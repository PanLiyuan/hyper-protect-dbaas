---

copyright:
  years: 2017
lastupdated: "2017-12-12"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}


# Using the RESTful API

## Before you begin

For authentication, you need an access token and a user ID to issue API requests to the DBaaS
Manager.

<ol>
<li>Generate an API key:
<ol>
<li>In the IBM Cloud dashboard, select **Manage > Security > Platform API Keys**.
<p>The Platform API Keys dialog is displayed.</p></li>
<li>In the Platform API Keys dialog, click **Create**.
<p>The Create API Key dialog is displayed.</p></li>
<li>In the Create API key dialog, enter a name for the API key and a description.</li>
<li>Click **Create**.</li>
<li>To download the API key, click **Download**.
<p>This operation returns a JSON file similar to this example:
<table>
  <tr>
    <td>
	<pre>
  {
  "name": "dbaasmgr",
  "description": "DBaaS Manager",
  "createdAt": "201...",
  "apiKey": "**Pt...Y**"
  }</pre>
	</td>
  </tr>
</table>
The value that is assigned to "apiKey" is your API key.
</p></li>
</ol>
</li>
<li>Obtain an access token and a user ID using the GET /auth/token operation:
<p>
<table>
  <tr>
    <td>
	<pre>
# curl -k -i -X GET https:/&sol;&lt;<em>DBaaSManager</em>&gt;&colon;&lt;<em>PortNumber</em>&gt;/api/v1/auth/token -H "api_key&colon;&lt;<em>APIkey</em>&gt;"</pre>
	</td>
  </tr>
</table>
</p>
<p>Where:
<dl>
  <dt> &lt;<em>DBaaSManager</em>&gt; </dt>
    <dd> Is the hostname of the DBaaS Manager. 
	<p>Valid host names for region `United Kingdom` are:</p>
<ul>
<li>mgmt02.hypersecuredbaas.ibm.com</li>
<li>mgmt03.hypersecuredbaas.ibm.com</li>
</ul> 
	<p>Valid host names for region `US South` are:</p>
<ul>
<li>mgmt06.hypersecuredbaas.ibm.com</li>
<li>mgmt07.hypersecuredbaas.ibm.com</li>
</ul> </dd>
  <dt> &lt;<em>PortNumber</em>&gt; </dt>
    <dd> Is the port number of the DBaaS Manager. The valid port number is:
<p>20000</p>  </dd>
  <dt> &lt;<em>APIkey</em>&gt; </dt>
    <dd> Is the API key as generated in step 1 </dd>
</dl>
</p>
<p>This operation returns an access token and a user ID similar to this example:
<table>
  <tr>
    <td>
	<pre>
	{
		"access_token": "eyJraWQiOiIyMD… …MCCwyLbg",
		"user_id": "925d4… 04a520"
	}</pre>
	</td>
  </tr>
</table>
</p>
</li>
<li>Save the values of the access token and the user ID.
</li>
</ol>

## Procedure

<ol>
<li>Specify the data of your request in JSON format.
</li>
<li>Send the API request to the DBaaS Manager.
<p>You can use a RESTful API client, such as cURL, to handle a request.
</p>
<p>DBaaS Managers are available at:
<table>
  <tr>
    <th> Host name </th>
    <th> Port number </th>
  </tr>
  <tr>
    <td> mgmt02.hypersecuredbaas.ibm.com </td>
    <td> 20000 </td>
  </tr>
    <tr>
    <td> mgmt03.hypersecuredbaas.ibm.com </td>
    <td> 20000 </td>
  </tr>
  <tr>
    <td> mgmt06.hypersecuredbaas.ibm.com </td>
    <td> 20000 </td>
  </tr>
    <tr>
    <td> mgmt07.hypersecuredbaas.ibm.com </td>
    <td> 20000 </td>
  </tr>
</table>
</p>	 
</li>
</ol>

<p>See **Reference > RESTful API** to get a list of methods and their parameters.
</p>

## Example

To create a database cluster, issue direct API calls based on a JSON formatted
configuration request. The cluster name is also used as the replica set name for the
database.

clusterconfig.json:
<table>
  <tr>
    <td>
	<pre>
  {
      "cluster": {
          "cluster_name": "my-cluster",
          "db_type": "mongodb",
          "replica_count": 3,
          "resource": {
              "cpu": 2,
              "memory": "16gib",
              "storage": "64gb"
          },  
          "db_admin": {
              "user_name": "admin",
              "password": "123456"
          }   
      }   
  }</pre>
	</td>
  </tr>
</table>

<table>
  <tr>
    <td>
	<pre>
# curl -k -i -X POST -d '@clusterconfig.json' -H "Content-Type: application/json" \
-H "accept-license-agreement:yes" -H "x-auth-token&colon;&lt;<em>accessToken</em>&gt;" \
https:/&sol;&lt;<em>DBaaSManager</em>&gt;&colon;&lt;<em>PortNumber</em>&gt;/api/v1&sol;&lt;<em>userID</em>&gt;/clusters/</pre>
	</td>
  </tr>
</table>

Where:
<dl>
<dt> &lt;<em>accessToken</em>&gt; </dt>
<dd>Is the obtained access token</dd>
<dt> &lt;<em>DBaaSManager</em>&gt; </dt>
<dd>Is the host name of a DBaaS Manager. Valid host names are:
<ul>
<li>mgmt02.hypersecuredbaas.ibm.com</li>
<li>mgmt03.hypersecuredbaas.ibm.com</li>
<li>mgmt06.hypersecuredbaas.ibm.com</li>
<li>mgmt07.hypersecuredbaas.ibm.com</li>
</ul>
</dd>
<dt> &lt;<em>PortNumber</em>&gt; </dt>
<dd>Is the port number of the DBaaS Manager. The valid port number is:
<p>20000</p>
</dd>
<dt> &lt;<em>usrID</em>&gt; </dt>
<dd>Is the obtained user ID</dd>
</dl>
