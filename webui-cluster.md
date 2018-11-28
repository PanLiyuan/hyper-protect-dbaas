---

copyright:
  years: 2017, 2018
lastupdated: "2018-11-26"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}


# Database clusters

## Creating a database cluster

<ol>
<li>Click the {{site.data.keyword.cloud_notm}} Hyper Protect DBaaS catalog entry to open the service configuration screen.</li>
<li>Enter the required values.
	<dl>
		<dt>Service name:</dt>
		<dd>A name for the database service.</dd>

    <dt>Choose a region/location to deploy in:</dt>
    <dd>Select the data center where the database will be located.</dd>

    <dt>Select a resource group:</dt>
    <dd>If no resource group is selectable, you can create one on the IBM Cloud dashboard.</dd>
    
    <dt>Tags:</dt>
    <dd>Tags are optional. See [Tagging resources](../../../docs/account/tagging.html#tagging) for more information about tagging.</dd>

		<dt>Cluster/Replicaset Name:</dt>
		<dd>A name for the database cluster. **Note:** The term "Replicaset Name" is specific to MongoDB.</dd>

		<dt>Database Admin Name:</dt>
		<dd>A user ID for the database administrator (DBA).
		<p>**Note:** The database administrator does not have SUPERUSER authority. The authorities of the database administrator are limited to INHERIT, CREATEROLE, CREATEDB, LOGIN, and REPLICATION.</p></dd>

		<dt>Database Admin Password:</dt>
		<dd>A password for the DBA user ID.</dd>

                <dt>Confirm Password:</dt>
                <dd>Confirm the password for the DBA user ID.</dd>

                <dt>License Agreement:</dt>
                <dd>After reading the license agreement, check the box to confirm your agreement.</dd>

                <dt>Pricing Plans:</dt>
		<dd>The pricing plans offer different pricing categories for databases of type MongoDB or PostgreSQL. Choose the one that best meets your needs.</dd>
	</dl>

</li>
<li>Click **Create**.

<p>The IBM Cloud dashboard is displayed.</p></li>

<li>Select the service to display the IBM Cloud Hyper Protect DBaaS dashboard.</li>
</ol>

## Listing all database clusters

Open the IBM Cloud dashboard to display a list of created database clusters.

<ol>
<li>Click the three bars in the upper left of the console.</li>
<li>Select Dashboard.</li>
</ol>

The displayed services contain a list of created database clusters.

## Showing detail information of a database cluster

* In the Manage tab of the cluster information, select the Overview tab.

The {{site.data.keyword.cloud_notm}} Hyper Protect DBaaS dashboard is displayed.

## Deleting a database cluster

In the cluster information:
1. Select the database cluster.
2. Click the three dots in the upper right corner.
3. Click **Delete**.
