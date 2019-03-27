---

copyright:
  years: 2017
lastupdated: "2018-11-26"

keywords: API key, IBM Cloud API, Platform API, key dialog

subcollection: hyper-protect-dbaas

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}


# Setting up authentication to use {{site.data.keyword.cloud_notm}} APIs

For authentication, you need an API key and an access token to issue API requests.
To obtain them, follow these instructions:

1. Generate an API key:

   a. In the {{site.data.keyword.cloud_notm}} dashboard, select **Manage > Security > Platform API Keys**.

      The Platform API Keys dialog is displayed.

   b. In the Platform API Keys dialog, click **Create**.

      The Create API Key dialog is displayed.

   c. In the Create API key dialog, enter a name for the API key and a description, and click **Create**.

   d. To download the API key, click **Download**. (Or to just display the API key, click **Show**.)

      This operation returns a JSON file similar to this example:

      ```
     {
     "name": "dbaasmgr",
     "description": "DBaaS Manager",
     "createdAt": "201...",
     "apiKey": "**Pt...Y**"
     }
     ```
     {:pre}

     **Important:** Make a note of the provided API key before you close the window.

2. To ensure secure data transfer, obtain a certificate authority (CA) file from https://api.hypersecuredbaas.ibm.com/cert.pem and copy it to an appropriate directory such as **/etc/ssl/certs/**.

3. Obtain an access token with this command:

   ```javascript
     curl -X POST \
     --header "Content-Type: application/x-www-form-urlencoded" --header "Accept: application/json" --data-urlencode "grant_type=urn:ibm:params:oauth:grant-type:apikey" --data-urlencode "response_type=cloud_iam" --data-urlencode "apikey=$API_KEY" "https://iam.<region-string>.bluemix.net/identity/token"
   ```
   {: codeblock}

   This operation returns output similar to this example:

   ```
   {
     "access_token": "eyJraWQiOiIyMDE3MT <very_long_token>",
     "refresh_token": "J1COhGO-G1SdtxwLZ <another_very_long_token>",
     "token_type": "Bearer",
     "expires_in": 3600,
     "expiration": 1533258247,
     "scope": "ibm openid"
   }
   ```
   {:pre}

   Save the access token provided for future use in {{site.data.keyword.cloud_notm}} API calls, such as when creating or listing a service instance.  

   **Note:** A user ID is not required when making {{site.data.keyword.cloud_notm}} API calls. When you make such calls, you will notice that the output identifies the owning account ID, which matches the DBaaS user ID that would be obtained with the same API key if you followed the instructions in [Setting up authentication to use DBaaS Manager APIs](../../../docs/services/hyper-protect-dbaas/api_auth.html).
