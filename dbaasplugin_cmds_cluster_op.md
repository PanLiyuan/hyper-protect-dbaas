---

copyright:
  years: 2017, 2018
lastupdated: "2018-11-20"

keywords: cluster operation command, cluster operation, cluster resource

subcollection: hyper-protect-dbaas

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}


# Cluster operation commands

This is the only cluster operation command:

- [cluster-show](#cluster_show)

## cluster-show command
{: #cluster_show}

### Description
{: #cluster_show_desc}

Shows the details of the specified cluster, including information about each replica member.  

### Usage
{: #cluster_show_use}
**ibmcloud dbaas cluster-show** *resource_name*

| Parameter        |  Description                                                    |
| ---------------- |  -------------------------------------------------------------- |
| *resource_name*  |  The name of the cluster resource. To find the resource name, use the {{site.data.keyword.cloud}} command **ibmcloud resource service-instances**. |
