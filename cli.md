---

copyright:
  years: 2017
lastupdated: "2017-03-12"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}

# Command-line interface
{: #commandlineinterface}

The Hyper Protect DBaaS command-line interface accepts several dmclient commands.
{: shortdesc}

To get a list of these dmclient commands, enter:

```
# ./dmclient help
```

## Cluster operation commands

These are the cluster operation commands:

- [cluster-create](#cluster-create)
- [cluster-list](#cluster-list)
- [cluster-show](#cluster-show)
- [cluster-delete](#cluster-delete)

### cluster-create command

#### Description

Creates a database cluster.

The command returns immediately with cluster status of BUILD. After about 30 seconds, a cluster status of RUNNING becomes available. To get the updated cluster status, run the [cluster-list](#cluster-list) or [cluster-show](#cluster-show) command.

This command requires that you accept the IBM license. Therefore, when issuing the command, preface it with the **\./dmclient --accept-license** option, as in this example:

**\./dmclient --accept-license cluster-create myClusterName user password**


#### Usage

**cluster-create** *cluster_name* *admin_name* *admin_password*

| Parameter        |  Description                                                    |
| :--------------- |  :------------------------------------------------------------- |
| *cluster_name*   |  The cluster name to create                                     |
| *admin_name*     |  The database administrator name to manage the database cluster |
| *admin_password* |  The password of database administrator                         |

### cluster-list command

#### Description

Lists all the clusters that have been created.

#### Usage
**cluster-list**

The command has no parameters.

### cluster-show command

#### Description

Shows the details of the specified cluster, including information about each replica member.  

#### Usage
**cluster-show** *cluster_id*

| Parameter        |  Description                                                    |
| :--------------- |  :------------------------------------------------------------- |
| *cluster_id*     |  The ID of the cluster, as shown in the [cluster-list](#cluster-list) command |


### cluster-delete command

#### Description

Deletes a cluster. Once the cluster is deleted, all the data is lost.

#### Usage

**cluster-delete** *cluster_id*

| Parameter        |  Description                                                    |
| :--------------- |  :------------------------------------------------------------- |
| *cluster_id*     |  The ID of the cluster, as shown in the [cluster-list](#cluster-list) command |

## Database operation commands

These are the database operation commands:

- [database-create](#database-create)
- [database-list](#database-list)
- [database-delete](#database-delete)

### database-create command

#### Description

Creates a database. For MongoDB, a collection must also be created with the database.

#### Usage

**database-create** *cluster_id* *database* *collection*

| Parameter        |  Description                 |
| :--------------- |  :---------------------------|
| *cluster_id*     |  The ID of the cluster       |
| *database*       |  The database name to create |
| *collection*     |  The collection name to create |


### database-list command

#### Description

Lists all the databases on the given cluster.

#### Usage

**database-list** *cluster_id*

| Parameter        |  Description                 |
| :--------------- |  :---------------------------|
| *cluster_id*     |  The ID of the cluster       |


### database-delete command

#### Description

Deletes a database.

#### Usage

**database-delete** *cluster_id* *database*

| Parameter        |  Description                 |
| :--------------- |  :---------------------------|
| *cluster_id*     |  The ID of the cluster       |
| *database*       |  The name of the database to delete. |



## Instance operation commands

These are the instance operation commands:

- [instance-stop](#instance-stop)
- [instance-start](#instance-start)
- [instance-restart](#instance-restart)

### instance-stop command

#### Description

Stops an instance (that is, a replication meber of the cluster).

#### Usage

**instance-stop** *instance_id*

| Parameter        |  Description                 |
| :--------------- |  :---------------------------|
| *instance_id*    |  The ID of the instance       |


### instance-start command

#### Description

Starts a stopped instance.

#### Usage

**instance-start** *instance_id*

| Parameter        |  Description                 |
| :--------------- |  :---------------------------|
| *instance_id*    |  The ID of the instance       |


### instance-restart command

#### Description

Restarts a running instance.

#### Usage

**instance-restart** *instance_id*

| Parameter        |  Description                 |
| :--------------- |  :---------------------------|
| *instance_id*    |  The ID of the instance       |



## Log operation commands

These are the log operation commands:

- [log-list](#log-list)
- [log-get](#log-get)


### log-list command

#### Description

Lists all the log files on an instance.

#### Usage

**log-list** *instance_id*

| Parameter        |  Description                  |
| :--------------- |  :--------------------------- |
| *instance_id*    |  The ID of the instance       |


### log-get command

#### Description

Downloads a log file from an instance.

#### Usage

**log-get** *instance_id* *filename*

| Parameter        |  Description                  |
| :--------------- |  :--------------------------- |
| *instance_id*    |  The ID of the instance       |
| *filename*       |  The name of the log file to download |



## Database user operation commands

These are the database user operation commands:

- [user-create](#user-create)
- [user-list](#user-list)
- [user-show](#user-show)
- [user-delete](#user-delete)


### user-create command

#### Description

Creates one or more database users.

#### Usage

**user-create** *cluster_id* *database.username* *password* \[*db_name* \[*db_name* ...\]\]

| Parameter        |  Description                  |
| :--------------- |  :--------------------------- |
| *cluster_id*     |  The ID of the cluster        |
| *database.username* | The authentication database name and a username to create, separated by a period |
| *password*       | The login password for this user. |
| *db_name*        | An optional parameter specifying the name of a database for which the user will have read and write access |


### user-list command

#### Description

Lists all the database users.

#### Usage

**user-list** *cluster_id*

| Parameter        |  Description                  |
| :--------------- |  :--------------------------- |
| *cluster_id*    |  The ID of the cluster       |


### user-show command

#### Description

Shows details about a database user.

#### Usage

**user-show** *cluster_id* *database.username*

| Parameter        |  Description                  |
| :--------------- |  :--------------------------- |
| *cluster_id*    |  The ID of the cluster       |
| *database.username* | The authentication database name and the user name, separated by a period |


### user-delete command

#### Description

Deletes a database user.

#### Usage

**user-delete** *cluster_id* *database.username*

| Parameter        |  Description                  |
| :--------------- |  :--------------------------- |
| *cluster_id*    |  The ID of the cluster       |
| *database.username* | The authentication database name and the user name, separated by a period |
