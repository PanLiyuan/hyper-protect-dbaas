---

copyright:
  years: 2017, 2018
lastupdated: "2018-06-07"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}


# User operation commands

These are the user operation commands:

- [user-create](#user_create)
- [user-list](#user_list)
- [user-show](#user_show)
- [user-delete](#user_delete)



## user-create command
{: #user_create}

### Description
{: #user_create_desc}

Creates a database user.

### Usage
{: #user_create_use}

**bx dbaas user-create** *resource_name* *auth_db.username* *password* [*db_name* [*db_name* [...]]]

| Parameter        |  Description                  |
| :--------------- |  :--------------------------- |
| *resource_name*     |  The name of the cluster resource.        |
| *auth_db.username* | The authentication database name and user name, separated by a period, to be assigned to the database user being created. This is how database users are identified for MongoDB. |
| *password*    |  The login password to be assigned to the user.      |
| *db_name*    |  Optional; this specifies a database for which the user will have read and write access.      |


## user-list command
{: #user_list}

### Description
{: #user_list_desc}

Lists all the database users.

### Usage
{: #user_list_use}

**bx dbaas user-list** *resource_name*

| Parameter        |  Description                  |
| :--------------- |  :--------------------------- |
| *resource_name*    |  The name of the cluster resource.      |
| *instance_id*    |  The ID of the instance.      |
| *filename*    |  The name of the user file to download.      |

## user-show command
{: #user_show}

### Description
{: #user_show_desc}

Shows details about a database user.

### Usage
{: #user_show_use}

**bx dbaas user-show** *resource_name* *auth_db.username*

| Parameter        |  Description                  |
| :--------------- |  :--------------------------- |
| *resource_name*    |  The name of the cluster resource.      |
| *auth_db.username*    |  The authentication database name and user name, separated by a period, that identify the database user. This is how database users are identified for MongoDB. |


## user-delete command
{: #user_delete}

### Description
{: #user_delete_desc}

Deletes a database user.

### Usage
{: #user_delete_use}

**bx dbaas user-delete** *resource_name* *auth_db.username*

| Parameter        |  Description                  |
| :--------------- |  :--------------------------- |
| *resource_name*    |  The name of the cluster resource.      |
| *auth_db.username*    |  The authentication database name and user name, separated by a period, that identify the database user. This is how database users are identified for MongoDB. |
