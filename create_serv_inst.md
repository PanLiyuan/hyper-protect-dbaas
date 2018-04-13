---

copyright:
  years: 2017
lastupdated: "2018-03-14"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}


# Create a service instance

To create a service instance, use the **bx resource service-instance-create** command, as shown in this example:

<pre><code class="hljs">~$ bx resource service-instance-create MyDBaaSIns03 hypersecuredbaas lite eu-gb -p
'{"name":"DaaSTestCLICluster03", "admin_name":"admin", "password":"111111", "confirm_password":"111111",
"db_type":"MongoDB", "license_agree":["agreed"]}'
</code></pre>

Where:

| Parameter        |  Definition                                                    |
| :--------------- |  :------------------------------------------------------------- |
| "MyDBaaSIns03"   |  The name of the service instance (replace with a name of your own choosing). | 
| "hypersecuredbaas" | The catalog name of Hyper Protect DBaaS. |
| "lite"             | The Lite service plan; a different service plan may lead to a different toll rate. |
| "eu-gb"            | The location where your new database will be located. (**Note:** Currently only **us-south** and **eu-gb** support Hyper Protect DBaaS.) |
| "-p"               | A valid JSON string, which must contain the parameters in the following table. |


| -p parameter       | Definition |
| :--------------- |  :------------------------------------------------------------- |
| "name"             | The name of your database cluster. |
| "db_type"          | The type of database service to be created. (**Note:** Currently only MongoDB is supported.) |
| "admin_name"       | The administrator's user name of the database to be created. |
| "password"         | The adminstrator's user password of the database to be created. |
| "confirm_password" | The same password. |
| "license_agree"    | A value of **agreed** indicates acceptance of the license agreement, which is required to use Hyper Protect DBaaS. |


After you enter the command, the state of the new service instance might temporarily appear as **inactive**, as shown in this example:

<pre><code class="hljs">Creating service instance MYDBaaSIns03 in resource group default
OK
Service instance MYDBaaSIns03 was created.
Name           Location   State      Type               Tags
MyDBaaSIns03   eu-gb      inactive   service_instance
~$
</code></pre>

This is because it takes a few minutes to prepare the cluster. 
To get an update of the cluster status, use the **bx resource service-instances** command, as shown in this example:

<pre><code class="hljs">~$ bx resource service-instances
Retrieving service instance in resource group default and a
m.com...
OK
Name           Location   State      Type               Tags
MyDBaaSIns03   eu-gb      active     service_instance
~$
</code></pre>




