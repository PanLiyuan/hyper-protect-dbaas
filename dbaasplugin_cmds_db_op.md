---

copyright:
  years: 2017, 2018
lastupdated: "2018-11-20"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}


# Database operation commands

These are the database operation commands:

- [database-create](#db_create)
- [database-list](#db_list)
- [database-delete](#db_delete)


## database-create command
{: #db_create}

### Description
{: #db_create_desc}

Creates a database and, optionally, a collection. 

**Note:** For MongoDB, a collection *must* be created with the database.

### Usage
{: #db_create_use}

**ibmcloud dbaas database-create** *resource_name* *database* [*collection*]

| Parameter        |  Description                  |
| :--------------- |  :--------------------------- |
| *resource_name*     |  The name of the cluster resource.        |
| *database.databasename* | The name of the database to create. |
| *collection*       | The name of the collection to create. Although this is an optional parameter, it is required for MongoDB. |


## database-list command
{: #db_list}

### Description
{: #db_list_desc}

Lists all the databases on the given cluster.

### Usage
{: #db_list_use}

**ibmcloud dbaas database-list** *resource_name*

| Parameter        |  Description                  |
| :--------------- |  :--------------------------- |
| *resource_name*    |  The name of the cluster       |


## database-delete command
{: #db_delete}

### Description
{: #db_delete_desc}

Deletes a database.

### Usage
{: #db_delete_use}

**ibmcloud dbaas database-delete** *resource_name* *database*

| Parameter        |  Description                  |
| :--------------- |  :--------------------------- |
| *resource_name*    |  The name of the cluster resource.       |
| *database* | The name of the database to delete. |
