---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-07"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}

# Migration

To migrate your existing IBM Cloud Hyper Protect databases from the IBM 
Cloud Hyper Protect DBaaS experimental service to the IBM Cloud Hyper Protect DBaaS
beta service, complete the following steps.
{: shortdesc}

## Procedure

To transfer the database information:

1. Deploy a new instance of the IBM Cloud Hyper Protect DBaaS service from the IBM Cloud Catalog.
For this, follow the steps as described in [Getting started](/docs/services/hyper-protect-dbaas?topic=hyper-protect-dbaas-gettingstarted#gettingstarted).

2. Verify that the new deployed instance is operational. Also, verify access 
to the interfaces that you are going to use as you did with the experimental 
service.

3. Copy all your data from the experimental environment to the new 
beta instance. To help you with this step, you can use database-specific tools. For example, you can   
back up the experimental environment and restore it to the new beta instance.

4. Verify that all data has been transferred successfully and the new 
beta instance is fully operational.

5. Adapt your local environment, such as scripts, to the new instance parameters, 
and ensure that any integrated access is redirected to the new instance.

6. Delete the experimental instance when you are confident that the migration 
has been completed successfully.

## Results

After a successful migration, the beta service provides enhanced functionality.
