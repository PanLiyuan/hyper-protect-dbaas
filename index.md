---

copyright:
  years: 2017, 2018
lastupdated: "2018-11-26"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# Getting started with {{site.data.keyword.cloud_notm}} Hyper Protect DBaaS
{: #gettingstarted}

{{site.data.keyword.cloud}} Hyper Protect DBaaS is an {{site.data.keyword.cloud_notm}} service that provides databases on demand.
It offers a flexible and scalable platform that allows you to quickly and easily
provision and manage your database of choice.
{: shortdesc}

This {{site.data.keyword.cloud_notm}} offering provides MongoDB and PostgreSQL database clusters. Each database
cluster comprises one primary/master database instance and two database instance
replicas/slaves that back up the primary/master one.

With {{site.data.keyword.cloud_notm}} Hyper Protect DBaaS, you can create database clusters in the {{site.data.keyword.cloud_notm}},
manage database instances, administer database users, and create and
monitor databases.

## Data security and privacy

{{site.data.keyword.IBM}} hosts your databases in a highly available and secure environment:
<ul>
<li>The underlying technologies prevent {{site.data.keyword.IBM_notm}} or a third party from being able to
access your data.
<p>The IBM Secure Service Container technology protects the system via a
tamper-proof environment. Access to the system is restricted and is only enabled
through well-defined RESTful APIs.</p></li>
<li>Data is encrypted at rest and in flight.</li>
<li>The system hardware, the system configuration, and the database setup ensure
high availability.</li>
</ul>

For more information, watch: 
<ul>
<li>[Data security and privacy using IBM Cloud Hyper Protect DBaaS - English version](https://www.youtube.com/watch?v=__IBP727IL8)</li>
<li>[Data security and privacy using IBM Cloud Hyper Protect DBaaS - Chinese version](https://v.youku.com/v_show/id_XMzc3ODQzMzYwMA==.html)</li>
</ul>


##Creating a database cluster

To create a database cluster, you simply enter the required values in the
{{site.data.keyword.cloud_notm}} Hyper Protect DBaaS service configuration screen and click **Create**.

After you have created the database cluster, {{site.data.keyword.IBM}} provides you the hostname and the port
numbers of the three created database instances. You can now use this information
and the user credentials you specified in the catalog to create and access your
databases.

##Managing the database cluster

In a database cluster, you can create databases, manage the database instances,
create or delete users, and get the database logs.

{{site.data.keyword.cloud_notm}} Hyper Protect DBaaS provides the DBaaS Manager, which manages and
intelligently schedules your requests based on the available resources.

You can address requests to the DBaaS Manager through one of these interfaces:
<ul>
<li>The [Web User Interface](../../../docs/services/hyper-protect-dbaas/webui-cluster.html)</li>
<li>The [DBaaS Manager APIs (for database cluster management)](../../../docs/services/hyper-protect-dbaas/api_genl_proc.html)</li>
<li>The [IBM Cloud APIs (for service instance management)](../../../docs/services/hyper-protect-dbaas/curl_create_serv_inst.html)</li>
<li>The [CLI plug-in with the IBM Cloud CLI tool](../../../docs/services/hyper-protect-dbaas/download_install.html)</li>
</ul>

## Accessing the database

After creating a MongoDB database, you can use the **mongo** shell, your favorite
MongoDB driver, or tools like MongoDB Compass to manage the database itself. 
For PostgreSQL, you can use **pgadmin** or your favorite PostgreSQL tool to manage the databases.

### Before you begin

To ensure secure data transfer, obtain a certificate authority (CA) file from
<https://api.hypersecuredbaas.ibm.com/cert.pem>, and copy it to the appropriate directory.

### Connecting to a database

The Hyper Protect DBaaS dashboard provides the necessary information to connect to a database.

#### mongo shell 

For MongoDB, you can run the mongo shell command that is provided at the Hyper Protect DBaaS dashboard:

1. Click the icon next to the command to copy it to your clipboard.
2. If the secure data connection fails with an SSL error, specify the obtained CA file to validate the server certificate. Add the parameter **--sslCAFile** to indicate the CA file.

<b>Example:</b>
<pre><code class="hljs"># mongo 'mongodb:/&sol;&lt;<em>Hostname_1</em>&gt;&colon;&lt;<em>PortNumber_1</em>&gt;,\
&lt;<em>Hostname_2</em>&gt;&colon;&lt;<em>PortNumber_2</em>&gt;,\
&lt;<em>Hostname_3</em>&gt;&colon;&lt;<em>PortNumber_3</em>&gt;/admin?replicaSet=&lt;<em>replicaSetName</em>&gt;' \
--ssl --username &lt;<em>userID</em>&gt; --password &lt;<em>password</em>&gt; --sslCAFile &lt;<em>CAFile</em>&gt;</code></pre>
Where:
<dl>
  <dt> &lt;<em>Hostname_i</em>&gt; </dt>
    <dd> Is the hostname of the database replica (<em>i=1,2,3</em>) </dd>
  <dt> &lt;<em>PortNumber_i</em>&gt; </dt>
    <dd> Is the port number of the database replica (<em>i=1,2,3</em>) </dd>
  <dt> &lt;<em>replicaSetName</em>&gt; </dt>
    <dd> Is the name of your returned replica set as specified in the Hyper Protect DBaaS dashboard </dd>
  <dt> &lt;<em>userID</em>&gt; </dt>
    <dd> Is the user ID for the DBA as specified in the
    service configuration screen </dd>
  <dt> &lt;<em>password</em>&gt; </dt>
    <dd> Is the password for the DBA user ID as specified in the
    service configuration screen </dd>
  <dt> &lt;<em>CAFile</em>&gt; </dt>
    <dd> Is the CA file cert.pem </dd>
</dl>

#### psql shell

For PostgreSQL, you can use this command:
<pre><code class="hljs">psql "host=&lt;<em>Hostname</em>&gt; user=&lt;<em>Username</em>&gt; port=&lt;<em>PortNumber</em>&gt; sslmode=verify-full sslrootcert=&lt;<em>CAFilePath</em>&gt;"</code></pre>
Where:
<dl>
  <dt> &lt;<em>Hostname</em>&gt; </dt>
    <dd> Is the hostname of the database cluster </dd>
  <dt> &lt;<em>Username</em>&gt; </dt> 
    <dd> Is the username for the DBA as specified in the service configuration screen </dd>
  <dt> &lt;<em>PortNumber</em>&gt; </dt>
    <dd> Is the port number of the database cluster </dd>
  <dt> &lt;<em>CAFilePath</em>&gt; </dt>
    <dd> Is the path of the CA file </dd>  
</dl>

**Note:** The **psql** command will not verify the database cluster certificate if the options **sslmode** and **sslrootcert** are not provided.

### Other tools

For other tools, such as MongoDB Compass and pgAdmin, Hyper Protect DBaaS supports *SSL server certificate validation* to connect to the host.  If needed, use the provided CA file. 
