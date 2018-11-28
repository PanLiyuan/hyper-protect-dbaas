---

copyright:
  years: 2017. 2018
lastupdated: "2018-11-20"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}


# Creating a service instance

To create a service instance, use the **ibmcloud resource service-instance-create** command, as shown in the following example. 
(**Note:** In Windows, it is recommended that you use a Bash terminal such as Cygwin or Git Bash to enter the command.)

```javascript
ibmcloud resource service-instance-create MyDBaaSIns03 hypersecuredbaas mongodb-m1-free eu-gb -p '{"name":"DBaaSTestCLICluster03", "admin_name":"admin","password":"Pass4user", "confirm_password":"Pass4user", "license_agree":["agreed"]}' 
```
{: codeblock}

Where the parameters have the following definitions:

| Parameter        |  Definition                                                    |
| :--------------- |  :------------------------------------------------------------- |
| "MyDBaaSIns03"   |  The name of the service instance (replace with a name of your own choosing). | 
| "hypersecuredbaas" | The catalog name of {{site.data.keyword.ihsdbaas_full}}. |
| "mongodb-m1-free"  | The plan name. Available plans are: **mongodb-m1-free**, **mongodb-m2**, **postgresql-m1-free**, and **postgresql-m2**. (**Note:** Plan names are case-sensitive.) |
| "us-south"            | The location where your new database will be located. (**Note:** Currently only **eu-gb**, **us-south**, and **us-east** support {{site.data.keyword.ihsdbaas_full}}.) |
| "-p"               | A valid JSON string, which must contain the parameters in the following table. |


| -p parameter       | Definition |
| :--------------- |  :------------------------------------------------------------- |
| "name"             | The name of your database cluster. |
| "admin_name"       | The administrator's user name of the database to be created. |
| "password"         | The administrator's user password of the database to be created. |
| "confirm_password" | The same password. |
| "license_agree"    | A value of **agreed** indicates acceptance of the license agreement, which is required to use {{site.data.keyword.ihsdbaas_full}}. |



After you enter the command, the state of the new service instance might temporarily appear as **inactive**, as shown in this example:

<pre><code class="hljs">Creating service instance MYDBaaSIns03 in resource group default
OK
Service instance MYDBaaSIns03 was created.
Name           Location   State      Type               Tags
MyDBaaSIns03   us-south   inactive   service_instance
~$
</code></pre>

This is because it takes a few minutes to prepare the cluster. 
To get an update of the cluster status, use the **ibmcloud resource service-instances** command, as shown in this example:

<pre><code class="hljs">~$ ibmcloud resource service-instances
Retrieving service instance in resource group default and a
m.com...
OK
Name           Location   State      Type               Tags
MyDBaaSIns03   us-south   active     service_instance
~$
</code></pre>




