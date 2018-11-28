---

copyright:
  years: 2017, 2018
lastupdated: "2018-11-20"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}


# Database user operation commands

These are the database user operation commands:

- [user-create](#user_create)
- [user-list](#user_list)
- [user-show](#user_show)
- [user-delete](#user_delete)


## user-create command
{: #user_create}

### Description
{: #user_create_desc}

Creates one or more database users.

### Usage
{: #user_create_use}

**user-create** *cluster_id* *database.username* *password* \[*db_name* \[*db_name* ...\]\]

| Parameter        |  Description                  |
| :--------------- |  :--------------------------- |
| *cluster_id*     |  The ID of the cluster        |
| *database.username* | The authentication database name and a username to create, separated by a period |
| *password*       | The login password for this user. |
| *db_name*        | An optional parameter specifying the name of a database for which the user will have read and write access |


## user-list command
{: #user_list}

### Description
{: #user_list_desc}

Lists all the database users.

### Usage
{: #user_list_use}

**user-list** *cluster_id*

| Parameter        |  Description                  |
| :--------------- |  :--------------------------- |
| *cluster_id*    |  The ID of the cluster       |


## user-show command
{: #user_show}

### Description
{: #user_show_desc}

Shows details about a database user.

### Usage
{: #user_show_use}

**user-show** *cluster_id* *database.username*

| Parameter        |  Description                  |
| :--------------- |  :--------------------------- |
| *cluster_id*    |  The ID of the cluster       |
| *database.username* | The authentication database name and the user name, separated by a period |


## user-delete command
{: #user_delete}

### Description
{: #user_delete_desc}

Deletes a database user.

### Usage
{: #user_delete_use}

**user-delete** *cluster_id* *database.username*

| Parameter        |  Description                  |
| :--------------- |  :--------------------------- |
| *cluster_id*    |  The ID of the cluster       |
| *database.username* | The authentication database name and the user name, separated by a period |
