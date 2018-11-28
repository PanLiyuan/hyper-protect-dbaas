---

copyright:
  years: 2017, 2018
lastupdated: "2018-11-20"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}


# Cluster operation commands

These are the cluster operation commands:

- [cluster-create](#cluster_create)
- [cluster-list](#cluster_list)
- [cluster-show](#cluster_show)
- [cluster-delete](#cluster_delete)

## cluster-create command
{: #cluster_create}

### Description
{: #cluster_create_desc}

Creates a database cluster.

The command returns immediately with cluster status of BUILD. After about 30 seconds, a cluster status of RUNNING becomes available. To get the updated cluster status, run the [cluster-list](#cluster_list) or [cluster-show](#cluster_show) command.

This command requires you to accept the IBM license. Therefore, when you enter the command, preface it with the **\./dmclient --accept-license** option, as in this example:

<pre><code class="hljs"># ./dmclient --accept-license cluster-create myClusterName user password
</code></pre>

### Usage
{: #cluster_create_use}

**cluster-create** *cluster_name* *admin_name* *admin_password*

| Parameter        |  Description                                                    |
| :--------------- |  :------------------------------------------------------------- |
| *cluster_name*   |  The cluster name to create                                     |
| *admin_name*     |  The database administrator name to manage the database cluster |
| *admin_password* |  The password of database administrator                         |

## cluster-list command
{: #cluster_list}

### Description
{: #cluster_list_desc}

Lists all the clusters that were created.

### Usage
{: #cluster_list_use}
**cluster-list**

The command has no parameters.

## cluster-show command
{: #cluster_show}

### Description
{: #cluster_show_desc}

Shows the details of the specified cluster, including information about each replica member.  

### Usage
{: #cluster_show_use}
**cluster-show** *cluster_id*

| Parameter        |  Description                                                    |
| :--------------- |  :------------------------------------------------------------- |
| *cluster_id*     |  The ID of the cluster, as shown in the [cluster-list](#cluster_list) command |


## cluster-delete command
{: #cluster_delete}

### Description
{: #cluster_delete_desc}

Deletes a cluster. When the cluster is deleted, all the data is lost.

### Usage
{: #cluster_delete_use}

**cluster-delete** *cluster_id*

| Parameter        |  Description                                                    |
| :--------------- |  :------------------------------------------------------------- |
| *cluster_id*     |  The ID of the cluster, as shown in the [cluster-list](#cluster_list) command |
