---

copyright:
  years: 2017
lastupdated: "2018-03-09"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}


# Delete a service instance

To review which services you have created, use this command:

<pre><code class="hljs">~$ bx resource service-instances
</code></pre>

If you wish to delete one of them, use the **bx resource service-instance-delete** command, as shown in this example:

<pre><code class="hljs">~$ bx resource service-instance-delete MyDBaaSIns03
Really delete the service instance MyDBaaSIns03 with ID crn:v1:bluemix:pub
da0e04a520:6884bf17-9950-450f-8bl1e-65487a72d812:: ?>
</code></pre>

As shown, the CLI tool asks you to confirm the deletion. 
To confirm, type **yes**.
