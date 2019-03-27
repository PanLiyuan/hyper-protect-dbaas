---

copyright:
  years: 2017, 2018
lastupdated: "2018-11-26"

keywords: log operation commands, operation commands, cluster resource, log file

subcollection: hyper-protect-dbaas

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}


# Log operation commands

These are the log operation commands:

- [log-list](#log_list)
- [log-get](#log_get)

## log-list command
{: #log_list}

### Description
{: #log_list_desc}

Lists all the log files on an instance.

### Usage
{: #log_list_use}

**ibmcloud dbaas log-list** *resource_name* *instance_id*

| Parameter        |  Description                  |
| ---------------- |  ---------------------------- |
| *resource_name*     |  The name of the cluster resource.        |
| *instance_id* | The ID of the instance. |


## log-get command
{: #log_get}

### Description
{: #log_get_desc}

Downloads a log file from an instance.

### Usage
{: #log_get_use}

**ibmcloud dbaas log-get** *resource_name* *instance_id* *filename*

| Parameter        |  Description                  |
| ---------------- |  ---------------------------- |
| *resource_name*    |  The name of the cluster resource.      |
| *instance_id*    |  The ID of the instance.      |
| *filename*    |  The name of the log file to download.      |
