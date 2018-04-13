---

copyright:
  years: 2017
lastupdated: "2017-03-12"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}


# Database clusters

## Creating a database cluster

<ol>
<li>Click on the {{site.data.keyword.cloud_notm}} Hyper Protect DBaaS catalog entry to open the service configuration screen.</li>
<li>Enter the required values.
	<dl>
		<dt>Service name:</dt>
		<dd>A name for the database service.</dd>

    <dt>Choose a region/location to deploy in:</dt>
    <dd>Select the data center where the database will be located.</dd>

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
    <dd>After reading the license agreement, check the box to confirm your agreement.</dd>

    <dt>Pricing:</dt>
		<dd>The current solution provides only one pricing category, which is free
		of charge. In later versions, you will be able to select the pricing category.</dd>
	</dl>
</li>
<li>Click **Create**.

<p>The IBM Cloud dashboard is displayed. You might have to refresh your browser to see the new cluster, 
which is listed in the Services section.</p></li>

<li>When you select the service, the cluster information is displayed.</li>
<li>In the Manage tab of the cluster information, click **OPEN**.
	<p>The IBM Cloud Hyper Protect DBaaS dashboard is displayed.</p></li>
</ol>

## Listing all database clusters

Open the IBM Cloud dashboard to display a list of created database clusters.

<ol>
<li>Click the three bars in the upper left of the console.</li>
<li>Select Dashboard.</li>
</ol>

The displayed services contain a list of created database clusters.

## Showing detail information of a database cluster

* In the Manage tab of the cluster information, click **OPEN**.

The {{site.data.keyword.cloud_notm}} Hyper Protect DBaaS dashboard is displayed.

## Deleting a database cluster

In the cluster information:
1. Select the database cluster.
2. Click the three dots in the upper right corner.
3. Click **Delete service**.
