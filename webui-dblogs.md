---

copyright:
  years: 2018
lastupdated: "2018-09-13"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}


# Database logging

After you have enabled database logging, you can view the logs using Kibana.

## Before you begin
{: #database_logging_byb}

1. Be sure to have access to at least one Cloud Foundry organization and space.
2. In the {{site.data.keyword.cloud_notm}} Hyper Protect DBaaS dashboard, select the Logging tab.

## Enabling database logging

In case the message "Logging is disabled" is displayed in the Logging tab:

1. Click **Enable**.
2. In the Enable Logging window, select the organization, space, and log type, then click **Submit**.

## Viewing database logs

1. Click **View in Kibana**.
2. In Kibana, select the same Cloud Foundry region, organization, and space which you selected to enable logging.
