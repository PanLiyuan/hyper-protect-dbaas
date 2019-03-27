---

copyright:
  years: 2017, 2019
lastupdated: "2019-03-25"

keywords: access token, DBaaS Manager APIs, API key

subcollection: hyper-protect-dbaas

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}


# Setting up authentication to use DBaaS Manager APIs

For authentication, you need an API key, an access token, and a user ID to issue API requests.
To do so, follow these instructions:

1. Generate an API key:

   a. In the {{site.data.keyword.cloud}} dashboard, select **Manage > Access (IAM)**.

      The Access (IAM) dashboard is displayed.

   b. In the side navigation panel of the Access (IAM) dashboard, select **{{site.data.keyword.cloud_notm}} API Keys**.

      The Platform API Keys dialog is displayed.

   c. In the Platform API Keys dialog, click **Create an {{site.data.keyword.cloud_notm}} API Key**.

      The Create API Key dialog is displayed.

   d. In the Create API key dialog, enter a name for the API key and a description and click **Create**.

   e. To download the API key, click **Download**. (Or to just display the API key, click **Show**.)

      This operation returns a JSON file similar to this example:

      ```
      {
       "name": "dbaasmgr",
       "description": "DBaaS Manager",
       "createdAt": "201...",
       "apiKey": "**Pt...Y**"
      }
       ```
      {: codeblock}

      The value that is assigned to "apiKey" is your API key. **Important:** Make a note of this value before you close the window.

2. To ensure secure data transfer, obtain a Certificate Authority (CA) file from the dashboard, and copy it to an appropriate directory such as **/etc/ssl/certs/**.

3. Get an access token and a user ID by using the GET /auth/token operation:

    ```curl
    curl -X GET -H "accept: application/json" -H "api_key: icGVY1*** ***UdfcIg4kzE" https://dbaas400.hyperprotectdbaas.cloud.ibm.com:20000/api/v1/auth/token
    ```
    {: pre}

    This operation returns an access token and a user ID similar to this example:

    ```
    {
     "access_token":"eyJraWQiOiIyMDE3MT*** ***3V4pMYrOvMniLA",
     "user_id":"e9433*** ***b188"
    }
    ```
    {: codeblock}

4. Save the values of the access token and the user ID for future use.
