---

copyright:
  years: 2018
lastupdated: "2018-11-26"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}


# Deleting a service instance

To review which services you have created, use this command:

<pre><code class="hljs">~$ ibmcloud resource service-instances
</code></pre>

If you want to delete one of them, use the **ibmcloud resource service-instance-delete** command, as shown in this example:

<pre><code class="hljs">~$ ibmcloud resource service-instance-delete MyDBaaSIns03
</code></pre>

The CLI tool asks you to confirm the deletion: 

<pre><code class="hljs">Really delete the service instance MyDBaaSIns03 with ID crn:v1:bluemix:pub
da0e04a520:6884bf17-9950-450f-8bl1e-65487a72d812:: ?>
</code></pre>

To confirm, type **yes**.
