---

copyright:
  years: 2017, 2018
lastupdated: "2018-11-20"

keywords: instance operation commands, instance operation, cluster resource

subcollection: hyper-protect-dbaas

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}


# Instance operation commands

These are the instance operation commands:

- [instance-stop](#instance_stop)
- [instance-start](#instance_start)
- [instance-restart](#instance_restart)


## instance-stop command
{: #instance_stop}

### Description
{: #instance_stop_desc}

Stops an instance (a replication member of the cluster).

### Usage
{: #instance_stop_use}

**ibmcloud dbaas instance-stop** *resource_name* *instance_id*

| Parameter        |  Description                  |
| ---------------- |  ---------------------------- |
| *resource_name*     |  The name of the cluster resource.        |
| *instance_id* | The ID of the instance. |


## instance-start command
{: #instance_start}

### Description
{: #instance_start_desc}

Starts a stopped instance.

### Usage
{: #instance_start_use}

**ibmcloud dbaas instance-start** *resource_name* *instance_id*

| Parameter        |  Description                  |
| ---------------- |  ---------------------------- |
| *resource_name*    |  The name of the cluster resource.      |
| *instance_id*    |  The ID of the instance.      |



## instance-restart command
{: #instance_restart}

### Description
{: #instance_restart_desc}

Restarts a running instance.

### Usage
{: #instance_restart_use}

**ibmcloud dbaas instance-restart** *resource_name* *instance_id*

| Parameter        |  Description                  |
| ---------------- |  ---------------------------- |
| *resource_name*    |  The name of the cluster resource.       |
| *instance_id* | The ID of the instance. |
