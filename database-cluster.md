---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-01"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:gif: .gif}
{:tip: .tip}

# Creating a highly available and secure database

To take full advantage of a highly available and secure database, you embed extra logic into your application. By using the provided code snippets, you can create, and access a MongoDB database. 

Currently, the supported programming language for using {{site.data.keyword.ihsdbaas_full}}
is Swift 4.0 with MongoKitten SDK 4.0.0.

## Step 1. Creating a database cluster
{: #create_dbcluster}

1. Access the {{site.data.keyword.ihsdbaas_full}} service configuration screen at
https://cloud.ibm.com/catalog/services/hyper-protect-dbaas.

2. Provide the following information:

	<dl>
		<dt>Service name:</dt>
		<dd>A name for the database service.</dd>

    <dt>Choose a region/location to deploy in:</dt>
    <dd>Select the data center where the database is located.</dd>

    <dt>Select a resource group:</dt>
    <dd>If no resource group is selectable, you can create one on the IBM Cloud dashboard.</dd>

		<dt>Cluster/Replicaset Name:</dt>
		<dd>A name for the database cluster.</dd>

		<dt>Database Admin Name:</dt>
		<dd>A user ID for the database administrator (DBA).</dd>

		<dt>Database Admin Password:</dt>
		<dd>A password for the DBA user ID.</dd>

    <dt>Confirm Database Admin Password:</dt>
    <dd>Confirm the password for the DBA user ID.</dd>

		<dt>Database Type:</dt>
		<dd>Select the database type. Currently, only MongoDB is supported.</dd>

    <dt>License Agreement:</dt>
    <dd>Read the license agreement, and check the box to confirm your agreement.</dd>

    <dt>Pricing:</dt>
		<dd>The current solution provides only one pricing category, which is free of charge. In later versions, you can select the pricing category.</dd>
	</dl>

3. Click **Create**.

  The {{site.data.keyword.cloud_notm}} dashboard is displayed. You might have to refresh your browser to see the new cluster, which is listed in the Services section.</p></li>

4. When you select the service, the cluster information is displayed.

5. In the Manage tab of the cluster information, click **OPEN**.

	The {{site.data.keyword.ihsdbaas_full}} dashboard is displayed.

6. Gather the host names and the port numbers of the three created database instances that belong to your database cluster. You need the host names, port numbers, and user credentials for steps in the [Connecting to the database](#connect_db) section.

## Step 2. Creating a project by using a starter kit
{: #create_with_starter}

You need a starter kit that is based on the server-side Swift web framework Kitura.

![Feature Details](videos/StarterKit.gif){: gif}

Use an existing project that was created from this starter kit, or create a new project.

1. Open the {{site.data.keyword.cloud_notm}} App Service dashboard at https://cloud.ibm.com/developer/appservice/dashboard.

2. Select the **Starter Kits** tab.

3. Select the **Swift Kitura** Backend for Frontend starter kit. Be sure not to confuse it with the Swift Kitura Basic web-App Starter Kit.
  The Create new project page is displayed.

4. Enter the project details and click **Create Project**.
  The project page is displayed.

5. On the projects page, click **Download Code**.

6. Expand the compressed file to your project directory.

## Step 3. Connecting to the database
{: #connect_db}

To ensure secure data transfer, download the certificate authority (CA) file from
https://api.hypersecuredbaas.ibm.com/cert.pem, and copy it to your project directory.

1. Change to your project directory where you have the expanded downloaded code files.

2. Create a JSON file that is named `cred.json` to store your access credentials to the database cluster.

3. Enter the values that are gathered from the steps in [Creating a database cluster](#create_dbcluster). The values must be specified in a single line.
  ```hljs
  {
  "uri": "mongodb://<admin_ID>:<admin_pwd>@<Hostname_1>:<PortNumber_1>,
  <Hostname_2>:<PortNumber_2>,<Hostname_3>:<PortNumber_3>
   /admin?ssl=true&ssl_ca_certs=/swift-project/<CA_file>"
  }
  ```
  {: codeblock}

  Where:
  <table>
  <tr>
    <th> Parameter </th>
    <th> Description </th>
  </tr>
  <tr>
    <td> &lt;<em>admin_ID</em>&gt; </td>
    <td> Is the user ID of the database administrator as specified in [Creating a database cluster](#create_dbcluster).
  </td>
  </tr>
  <tr>
    <td> &lt;<em>admin_pwd</em>&gt; </td>
    <td> Is the user ID of the administrator password as specified in [Creating a database cluster](#create_dbcluster). </td>
  </tr>
  <tr>
    <td> &lt;<em>Hostname_i</em>&gt; </td>
    <td> Is a database replica <em>i</em> (<em>i</em>=1,2,3) as returned in [Creating a database cluster](create_dbcluster). </td>
  </tr>
  <tr>
    <td> &lt;<em>PortNumber_i</em>&gt; </td>
    <td> Is a port number <em>i</em> (<em>i</em>=1,2,3) as returned in [Creating a database cluster](#create_dbcluster). </td>
  </tr>
  <tr>
    <td> &lt;<em>CA_file</em>&gt; </td>
    <td> Is the file name of the downloaded CA file. During deployment, it is copied to the directory `/swift-project`.</td>
  </tr>
  </table>

4. Edit the `Package.swift` file to add package dependencies for the use of the
MongoKitten SDK.

  * In the dependencies section, add the following line:
   ```swift
   .package(url: "https://github.com/OpenKitten/MongoKitten.git", from: "4.0.0"),
   ```
   {: codeblock}

  * In the targets section, add the dependency "MongoKitten" to the following line. **Note:** The values must be specified in a single line.
   ```swift
   .target(name: "Application", dependencies: [ "Kitura",
   "CloudEnvironment","SwiftMetrics","Health","MongoKitten", ]),
   ```
   {: codeblock}

5. Edit the `Sources/Application/Application.swift` file to initialize connectivity to MongoDB by using MongoKitten.

  * Import the MongoKitten SDK:
    ```swift
	  import MongoKitten
	  ```
	  {: codeblock}

  * Add the class `ApplicationServices`:
    ```swift
	  cclass ApplicationServices {
	  /* Service references */
	  public let mongoDBService: MongoKitten.Database
	  public let myCredFile = "/swift-project/cred.json"

    public init() throws {
        /* Read credentials from json file cred.json */
        struct ResponseData: Decodable {
            var uri: String
        }
        let data = try? Data(contentsOf: URL(fileURLWithPath: myCredFile))
        let decoder = JSONDecoder()
        let jsonData = try decoder.decode(ResponseData.self, from: data!)

        /* Run service initializers */
        let server = try Server(jsonData.uri)
        mongoDBService = MongoKitten.Database(named: "admin", atServer: 		server)
    }
	}
	```
	{: codeblock}

  * In the public class `App`, add the following lines to initialize the database connection:
    ```swift
	  public class App {
	  ...
	  let services: ApplicationServices

	  public init() throws {
	  /* Services */
	  services = try ApplicationServices()
	  }
	  ...
    ```
    {: codeblock}

## Step 4. Verifying the database connection
{: #verify_database}

1. Verify your database connection by editing the file `Sources/Application/Application.swift` to add a command to test the database connection.
For example, add the following command in the `class ApplicationServices`:

	```swift
		class ApplicationServices {
		    ...
		    public init() throws {
		        ...
		        let server = try Server(jsonData.uri)
		        mongoDBService = MongoKitten.Database(named: "admin", atServer: server)
		        if server.isConnected {
		            print("Connected to mongodb: " + String(describing: mongoDBService))
		        }
		        ...
		    }
		}
	```
	{: codeblock}

After you deploy your application in [Step 6](#use-step6), the following message is displayed, if your connection to the database succeeds:

```
...
Connected to mongodb:
MongoKitten.Database&lt;mongodb:/&sol;&lt;<em>Hostname_1</em>&gt;&colon;&lt;<em>PortNumber_1</em>&gt;,&lt;<em>Hostname_2</em>&gt;&colon;&lt;<em>PortNumber_2</em>&gt;,&lt;<em>Hostname_3</em>&gt;&colon;&lt;<em>PortNumber_3</em>&gt;/admin&gt;
...
```
{: screen}

## Step 5. Embedding your application code
{: #embed_appcode}

You can now add your own application code to the project. For more information about working with the MongoKitten API, see http://beta.openkitten.org/tutorials/.

## Step 6. Deploying your application
{: #deploy_app}

You can run the application [locally](/docs/swift/create_app_cli.html#swift-install-tools) with the necessary build tools, or deploy to {{site.data.keyword.cloud_notm}}.

To create a deployment toolchain in the dashboard, click **Deploy to Cloud**. Set up your deployment method according to the instructions for the method you choose:
  * **Deploy to [Kubernetes](/docs/apps/deploying/containers.html#containers)**. This option creates a cluster of hosts, called worker nodes, to deploy and manage highly available application containers. You can create a cluster or deploy to an existing cluster.
  * **Deploy to Cloud Foundry**. This option deploys your cloud-native app without you needing to manage the underlying infrastructure. If your account has access to {{site.data.keyword.cfee_full_notm}}, you can select a deployer type of either **[Public Cloud](/docs/cloud-foundry-public/about-cf.html#about-cf)** or **[Enterprise Environment](/docs/cloud-foundry-public/cfee.html#cfee)**, which you can use to create and manage isolated environments for hosting Cloud Foundry applications exclusively for your enterprise.
  * **Deploy to a [Virtual Server](/docs/apps/vsi-deploy.html#vsi-deploy)**. This option provisions a virtual server instance, loads an image that includes your app, creates a DevOps toolchain, and initiates the first deployment cycle for you.