---

copyright:
  years: 2017, 2018
lastupdated: "2017-04-23"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}


# Installing dmclient

Use the command-line interface (CLI) to issue API calls to the DBaaS Manager.
IBM provides the CLI tool dmclient for download.

## Before you begin
{: #installing_dmclient_byb}

<ol>
<li>Make sure you have installed a Python version of at least 2.7.0.
<p>See https://www.python.org for download.</p></li>
<li>Make sure you have installed the library python-requests.
<p>See http://docs.python-requests.org/en/master/ for installation.</p></li>
</ol>

## Step 1: Obtain dmclient

To obtain dmclient, download all available files from <https://github.com/IBM/dmclient>.

Later, you can run dmclient from the directory where the files are located.

## Step 2: Generate an API key

To authenticate API requests, you need an API key.

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

## Step 3: Define a client environment script

To identify suitable API targets, define environment variables. You can use client
environment scripts for setting environment variables.

### About this task

Define the following environment variables:
<dl>
  <dt> DBAAS_MANAGER_IP </dt>
    <dd> Hostname or IP address of the DBaaS Manager. Valid host names are:	       
      <ul>
        <li> REGION EU-GB
	  <ul>
            <li> mgmt02.hypersecuredbaas.ibm.com</li>
            <li> mgmt03.hypersecuredbaas.ibm.com</li>
          </ul>
        </li>

        <li> REGION US-SOUTH		
          <ul>
            <li> mgmt06.hypersecuredbaas.ibm.com</li>
            <li> mgmt07.hypersecuredbaas.ibm.com</li>
	  </ul>
        </li>
      </ul>		
	</dd>
  <dt> DBAAS_MANAGER_PORT </dt>
    <dd> Port number of the DBaaS Manager. The valid port number is:
<p>20000</p> </dd>
  <dt> API_KEY </dt>
    <dd> API key as generated in step 2</dd>
  <dt> CPU_NUMBER </dt>
    <dd> The requested number of CPUs </dd>
  <dt> MEMORY_SIZE </dt>
    <dd> The requested memory size </dd>
  <dt> STORAGE_SIZE </dt>
    <dd> The requested storage size </dd>
</dl>

### Procedure
{: #installing_dmclient_proc}

Create a client environment script named openrc.

Enter the following lines:
<table role="presentation">
  <tr>
    <td> # export DBAAS_MANAGER_IP=<*DBaaS_mgr_host_name*> </td>
  </tr><tr>
    <td> # export DBAAS_MANAGER_PORT=<*DBaaS_mgr_port_number*> </td>
  </tr><tr>
    <td> # export API_KEY=<*api_key*> </td>
  </tr><tr>
    <td> # export CPU_NUMBER=<*cpu_number*> </td>
  </tr><tr>
    <td> # export MEMORY_SIZE=<*memory_size*> </td>
  </tr><tr>
    <td> # export STORAGE_SIZE=<*storage_size*> </td>
  </tr>
</table>

<p>To set the environment variables, load the client environment script:
<pre><code class="hljs"># source openrc
</code></pre>
</p>
