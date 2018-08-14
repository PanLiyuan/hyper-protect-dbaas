---

copyright:
  years: 2017
lastupdated: "2018-08-13"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}


# General instructions for using the DBaaS Manager APIs

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
    <th> Region </th>
  </tr>
  <tr>
    <td> mgmt02.hypersecuredbaas.ibm.com </td>
    <td> 20000 </td>
    <td> eu-gb </td>
  </tr>
    <tr>
    <td> mgmt03.hypersecuredbaas.ibm.com </td>
    <td> 20000 </td>
    <td> eu-gb </td>
  </tr>
  <tr>
    <td> mgmt06.hypersecuredbaas.ibm.com </td>
    <td> 20000 </td>
    <td> us-south </td>
  </tr>
    <tr>
    <td> mgmt07.hypersecuredbaas.ibm.com </td>
    <td> 20000 </td>
    <td> us-south </td>
  </tr>
</table>
</p>	 
</li>
</ol>

<p>To link to documentation for the DBaaS Management APIs (methods and parameters), see the **REFERENCE** heading in the navigation menu at:  https://console.bluemix.net/docs/services/hyper-protect-dbaas/index.html#gettingstarted
</p>

## Example

To create a database cluster, issue direct API calls based on a JSON formatted
configuration request. The cluster name is also used as the replica set name for the
database.

clusterconfig.json:

```javascript
  {
      "cluster": {
          "region": "us-south",
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
  }
```
{: codeblock}

```javascript
curl -k -i -X POST -d '@clusterconfig.json' -H "Content-Type: application/json" -H "accept-license-agreement:yes" -H "x-auth-token: <accessToken>" https://<DBaaSManager>:<PortNumber>/api/v1/<userID>/clusters
```
{:codeblock}

Where:
<dl>
<dt> &lt;<em>accessToken</em>&gt; </dt>
<dd>Is the previously-obtained access token; see [Setting up authentication to use DBaaS Manager APIs](../../../docs/services/hyper-protect-dbaas/api_auth.html). (**Note:** If the access token has expired, return to those instructions and request a new token.) </dd>
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
<dd>Is the previously-obtained user ID.</dd>
</dl>
