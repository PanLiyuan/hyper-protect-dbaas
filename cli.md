---

copyright:
  years: 2017
lastupdated: "2017-11-20"

keywords: cluster operation commands, database cluster, operation commands, dmclient commands

subcollection: hyper-protect-dbaas

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}

# Command-line interface
{: #commandlineinterface}

The {{site.data.keyword.ihsdbaas_full}} command-line interface accepts several dmclient commands.
{: shortdesc}

To get a list of these dmclient commands, enter:

```
# ./dmclient help
```

## Cluster operation commands
{: #cluster-operation-commands}

These are the cluster operation commands:

- [cluster-create](#cluster-create)
- [cluster-list](#cluster-list)
- [cluster-show](#cluster-show)
- [cluster-delete](#cluster-delete)

### cluster-create command
{: #cluster-create-command}

#### Description
{: #cluster-create-command-description}

Creates a database cluster.

The command returns immediately with cluster status of BUILD. After about 30 seconds, a cluster status of RUNNING becomes available. To get the updated cluster status, run the [cluster-list](#cluster-list) or [cluster-show](#cluster-show) command.

This command requires that you accept the {{site.data.keyword.IBM}} license. Therefore, when issuing the command, preface it with the **\./dmclient --accept-license** option, as in this example:

**\./dmclient --accept-license cluster-create myClusterName user password**


#### Usage
{: #cluster-create-command-usage}

**cluster-create** *cluster_name* *admin_name* *admin_password*

| Parameter        |  Description                                                    |
| ---------------- |  -------------------------------------------------------------- |
| *cluster_name*   |  The cluster name to create                                     |
| *admin_name*     |  The database administrator name to manage the database cluster |
| *admin_password* |  The password of database administrator                         |

### cluster-list command
{: #cluster-list-command}

#### Description
{: #cluster-list-command-description}

Lists all the clusters that have been created.

#### Usage
{: #cluster-list-command-usage}

**cluster-list**

The command has no parameters.

### cluster-show command
{: #cluster-show-command}

#### Description
{: #cluster-show-command-description}

Shows the details of the specified cluster, including information about each replica member.  

#### Usage
{: #cluster-show-command-usage}

**cluster-show** *cluster_id*

| Parameter        |  Description                                                    |
| ---------------- |  -------------------------------------------------------------- |
| *cluster_id*     |  The ID of the cluster, as shown in the [cluster-list](#cluster-list) command |


### cluster-delete command
{: #cluster-delete-command}

#### Description
{: #cluster-delete-command-description}

Deletes a cluster. Once the cluster is deleted, all the data is lost.

#### Usage
{: #cluster-delete-command-usage}

**cluster-delete** *cluster_id*

| Parameter        |  Description                                                    |
| ---------------- |  -------------------------------------------------------------- |
| *cluster_id*     |  The ID of the cluster, as shown in the [cluster-list](#cluster-list) command |

## Database operation commands
{: #database-operation-commands}

These are the database operation commands:

- [database-create](#database-create)
- [database-list](#database-list)
- [database-delete](#database-delete)

### database-create command
{: #database-create-command}

#### Description
{: #database-create-command-description}

Creates a database. For MongoDB, a collection must also be created with the database.

#### Usage
{: #database-create-command-usage}

**database-create** *cluster_id* *database* *collection*

| Parameter        |  Description                 |
| ---------------- |  ----------------------------|
| *cluster_id*     |  The ID of the cluster       |
| *database*       |  The database name to create |
| *collection*     |  The collection name to create |


### database-list command
{: #database-list-command}

#### Description
{: #database-list-command-description}

Lists all the databases on the given cluster.

#### Usage
{: #database-list-command-usage}

**database-list** *cluster_id*

| Parameter        |  Description                 |
| ---------------- |  ----------------------------|
| *cluster_id*     |  The ID of the cluster       |


### database-delete command
{: #database-delete-command}

#### Description
{: #database-delete-command-description}

Deletes a database.

#### Usage
{: #database-delete-command-usage}

**database-delete** *cluster_id* *database*

| Parameter        |  Description                 |
| ---------------- |  ----------------------------|
| *cluster_id*     |  The ID of the cluster       |
| *database*       |  The name of the database to delete. |



## Instance operation commands
{: #instance-operation-commands}

These are the instance operation commands:

- [instance-stop](#instance-stop)
- [instance-start](#instance-start)
- [instance-restart](#instance-restart)

### instance-stop command
{: #instance-stop-command}

#### Description
{: #instance-stop-command-description}

Stops an instance (that is, a replication member of the cluster).

#### Usage
{: #instance-stop-command-usage}

**instance-stop** *instance_id*

| Parameter        |  Description                 |
| ---------------- |  ----------------------------|
| *instance_id*    |  The ID of the instance       |


### instance-start command
{: #instance-start-command}

#### Description
{: #instance-start-command-description}

Starts a stopped instance.

#### Usage
{: #instance-start-command-usage}

**instance-start** *instance_id*

| Parameter        |  Description                 |
| ---------------- |  ----------------------------|
| *instance_id*    |  The ID of the instance       |


### instance-restart command
{: #instance-restart-command}

#### Description
{: #instance-restart-command-description}

Restarts a running instance.

#### Usage
{: #instance-restart-command-usage}

**instance-restart** *instance_id*

| Parameter        |  Description                 |
| ---------------- |  ----------------------------|
| *instance_id*    |  The ID of the instance       |



## Log operation commands
{: #log-operation-commands}

These are the log operation commands:

- [log-list](#log-list)
- [log-get](#log-get)


### log-list command
{: #log-list-command}

#### Description
{: #log-list-command-description}

Lists all the log files on an instance.

#### Usage
{: #log-list-command-usage}

**log-list** *instance_id*

| Parameter        |  Description                  |
| ---------------- |  ---------------------------- |
| *instance_id*    |  The ID of the instance       |


### log-get command
{: #log-get-command}

#### Description
{: #log-get-command-description}

Downloads a log file from an instance.

#### Usage
{: #log-get-command-usage}

**log-get** *instance_id* *filename*

| Parameter        |  Description                  |
| ---------------- |  ---------------------------- |
| *instance_id*    |  The ID of the instance       |
| *filename*       |  The name of the log file to download |



## Database user operation commands
{: #database-user-operation-commands}

These are the database user operation commands:

- [user-create](#user-create)
- [user-list](#user-list)
- [user-show](#user-show)
- [user-delete](#user-delete)


### user-create command
{: #user-create-command}

#### Description
{: #user-create-command-description}

Creates one or more database users.

#### Usage
{: #user-create-command-usage}

**user-create** *cluster_id* *database.username* *password* \[*db_name* \[*db_name* ...\]\]

| Parameter        |  Description                  |
| ---------------- |  ---------------------------- |
| *cluster_id*     |  The ID of the cluster        |
| *database.username* | The authentication database name and a username to create, separated by a period |
| *password*       | The login password for this user. |
| *db_name*        | An optional parameter specifying the name of a database for which the user will have read and write access |


### user-list command
{: #user-list-command}

#### Description
{: #user-list-command-description}

Lists all the database users.

#### Usage
{: #user-list-command-usage}

**user-list** *cluster_id*

| Parameter        |  Description                  |
| ---------------- |  ---------------------------- |
| *cluster_id*    |  The ID of the cluster       |


### user-show command
{: #user-show-command}

#### Description
{: #user-show-command-description}

Shows details about a database user.

#### Usage
{: #user-show-command-usage}

**user-show** *cluster_id* *database.username*

| Parameter        |  Description                  |
| ---------------- |  ---------------------------- |
| *cluster_id*    |  The ID of the cluster       |
| *database.username* | The authentication database name and the user name, separated by a period |


### user-delete command
{: #user-delete-command}

#### Description
{: #user-delete-command-description}

Deletes a database user.

#### Usage
{: #user-delete-command-usage}

**user-delete** *cluster_id* *database.username*

| Parameter        |  Description                  |
| ---------------- |  ---------------------------- |
| *cluster_id*    |  The ID of the cluster       |
| *database.username* | The authentication database name and the user name, separated by a period |
