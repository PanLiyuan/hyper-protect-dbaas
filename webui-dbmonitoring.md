---

copyright:
  years: 2018
lastupdated: "2018-11-26"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}


# Database monitoring

After you have enabled database monitoring, you can view the database metrics using Grafana.

## Before you begin
{: #database_logging_byb}

<ol>
<li>Be sure to have access to at least one Cloud Foundry organization and space. The organization and space must be in the location of your database cluster, except database clusters residing in Washington (us-east), which need access to an organization and space in Dallas (us-south) for monitoring. 

<p>For information about how to obtain such access, see https://console.bluemix.net/docs/iam/mngcf.html#mngcf.</p>
</li>

<li>In the {{site.data.keyword.cloud_notm}} Hyper Protect DBaaS dashboard, select the Monitoring tab.
</li>
</ol>

## Enabling database monitoring

In case the message "Monitoring is disabled" is displayed in the Monitoring tab:

1. Click **Enable**.
2. In the Enable Monitoring window, select your organization and space, then click **Submit**.


## Viewing database metrics

There are two ways to view the metrics in Grafana:

- Copy the displayed link, then open a new tab or window and paste the link to the browser.
- Click **View in Grafana**.

To display the metrics in a new dashboard in Grafana, select the upper left icon, then select **Dashboards > New**. 

For more information about using Grafana, see https://console.bluemix.net/docs/services/cloud-monitoring/index.html#getting-started-with-ibm-cloud-monitoring.
