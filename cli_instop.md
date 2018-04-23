---

copyright:
  years: 2017, 2018
lastupdated: "2018-04-23"

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

Stops an instance (that is, a replication member of the cluster).

### Usage
{: #instance_stop_use}

**instance-stop** *instance_id*

| Parameter        |  Description                 |
| :--------------- |  :---------------------------|
| *instance_id*    |  The ID of the instance       |


## instance-start command
{: #instance_start}

### Description
{: #instance_start_desc}

Starts a stopped instance.

### Usage
{: #instance_start_desc}

**instance-start** *instance_id*

| Parameter        |  Description                 |
| :--------------- |  :---------------------------|
| *instance_id*    |  The ID of the instance       |


## instance-restart command
{: #instance_restart}

### Description
{: #instance_restart_desc}

Restarts a running instance.

### Usage
{: #instance_restart_use}

**instance-restart** *instance_id*

| Parameter        |  Description                 |
| :--------------- |  :---------------------------|
| *instance_id*    |  The ID of the instance       |
