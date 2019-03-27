---

copyright:
  years: 2017, 2019
lastupdated: "2019-02-07"

keywords: DBaaS Manager APIs, DBaaS Manager, API request

subcollection: hyper-protect-dbaas

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}


# General instructions for using the DBaaS Manager APIs
{: #gen_inst_mgr_apis}
<ol>
<li>Specify the data of your request in JSON format.
</li>
<li>Send the API request to the DBaaS Manager.
<p>You can use a RESTful API client, such as cURL, to handle a request.
</p>
<p>DBaaS Managers are available here:
<table>
  <tr>
    <th> Host name </th>
    <th> Port number </th>
    <th> Region </th>
    <th> City </th>
  </tr>
  <tr>
    <td> dbaas400.hyperprotectdbaas.cloud.ibm.com </td>
    <td> 20000 </td>
    <td> us-east </td>
    <td> Washington </td>
  </tr>
</table>
</p>	 
</li>
</ol>

<p>To link to documentation for the DBaaS Management APIs (methods and parameters), see https://cloud.ibm.com/apidocs/hyper-protect-dbaas
</p>

## Example

To create a service instance, issue direct API calls based on a JSON formatted
configuration request.

clusterconfig.json contents are shown here:

```javascript
{
  "name": "my-cluster",
  "resource_group": "default",
  "plan": "mongodb-m1-free",
  "admin_name": "admin",
  "password": "Passw0rd"
}
```
{: codeblock}

Where:
<dl>
<dt> &lt;<em>name</em>&gt; </dt>
<dd>The name of the service instance to be created. </dd>
<dt> &lt;<em>resource_group</em>&gt; </dt>
<dd>Is the resource group of the new service instance.
</dd>
<dt> &lt;<em>plan</em>&gt; </dt>
<dd>Is the chosen pricing plan.
</dd>
<dt> &lt;<em>admin_name</em>&gt; </dt>
<dd>Is the user ID for the database administrator (DBA).</dd>
<dt> &lt;<em>password</em>&gt; </dt>
<dd>Is the password for the DBA user ID.</dd>
</dl>

```javascript
curl -k -i -X POST -H "accept-license-agreement: yes" -H "Content-Type: application/json" -H "x-auth-token: <accessToken>" -d '@clusterconfig.json' https://<DBaaSManager>:<PortNumber>/api/v1/services
```
{:codeblock}

Where:
<dl>
<dt> &lt;<em>accessToken</em>&gt; </dt>
<dd>Is the previously obtained access token; see [Setting up authentication to use DBaaS Manager APIs](/docs/services/hyper-protect-dbaas?topic=hyper-protect-dbaas-setting-up-authentication-to-use-dbaas-manager-apis#setting-up-authentication-to-use-dbaas-manager-apis). (**Note:** If the access token has expired, return to those instructions and request a new token.) </dd>
<dt> &lt;<em>DBaaSManager</em>&gt; </dt>
<dd>Is the host name of a DBaaS Manager. Valid host names are listed in the table above.
</dd>
<dt> &lt;<em>PortNumber</em>&gt; </dt>
<dd>Is the port number of the DBaaS Manager. This is the valid port number:
<p>20000</p>
</dd>
<dt> &lt;<em>userID</em>&gt; </dt>
<dd>Is the previously obtained user ID.</dd>
</dl>

**Note:** The database administrator does not have SUPERUSER authority.
The authorities of the database administrator are limited to INHERIT, CREATEROLE, CREATEDB, LOGIN, and REPLICATION.
