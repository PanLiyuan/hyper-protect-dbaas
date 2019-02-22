---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-21"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}


# Database logging

After you have enabled database logging, you can view the logs using Kibana.

## Before you begin
{: #database_logging_byb}

<ol>
<li>Be sure to have access to at least one Cloud Foundry organization and space. The organization and space must be in the location of your database cluster, except database clusters residing in Washington (us-east), which need access to an organization and space in Dallas (us-south) for logging. 

<p>For information about how to obtain such access, see https://cloud.ibm.com/docs/iam?topic=iam-mngcf#mngcf.</p>
</li>

<li>Make sure that all tree instances of the database cluster are running.
</li>

<li>In the {{site.data.keyword.cloud_notm}} Hyper Protect DBaaS dashboard, select the Logging tab. 
**Note:** If you do not have the access mentioned in Step 1, you will receive this error message:
"No available Cloud Foundry organization or space found. To enable logging, please request the access 
to at least one Cloud Foundry organization and space!" 
</li>
</ol>

## Enabling database logging

In case the message "Logging is disabled" is displayed in the Logging tab:

1. Click **Enable**.
2. In the Enable Logging window, select the organization, space, and log type, then click **Submit**.

**Note:** Currently, the only log types available are **audit log** and **database log**.

## Viewing database logs

There are two ways to view the logs in Kibana:

* Copy the displayed link, then open a new tab or window and paste the link to the browser.
* Click **View in Kibana**.

In Kibana, select the same Cloud Foundry region, organization, and space which you selected to enable logging.

For more information, see https://cloud.ibm.com/docs/services/CloudLogAnalysis?topic=cloudloganalysis-getting-started-with-cla#getting-started-with-cla.
