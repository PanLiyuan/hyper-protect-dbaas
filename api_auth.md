---

copyright:
  years: 2017
lastupdated: "2018-08-10"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}


# Setting up authentication to use DBaaS Manager APIs

For authentication, you need an API key, an access token, and a user ID to issue API requests. 
To do so, follow these instructions:

1. Generate an API key:

   a. In the IBM Cloud dashboard, select **Manage > Security > Platform API Keys**. 
   
      The Platform API Keys dialog is displayed.
      
   b. In the Platform API Keys dialog, click **Create**.
   
      The Create API Key dialog is displayed.
      
   c. In the Create API key dialog, enter a name for the API key and a description and click **Create**.
   
   d. To download the API key, click **Download**. (Or to just display the API key, click **Show**.)
   
      This operation returns a JSON file similar to this example:
      
      <pre>
      {
       "name": "dbaasmgr",
       "description": "DBaaS Manager",
       "createdAt": "201...",
       "apiKey": "**Pt...Y**"
       }
      </code></pre>
  
      The value that is assigned to "apiKey" is your API key. **Important:** Make a note of this value before you close the window.
      
2. To ensure secure data transfer, obtain a Certificate Authority (CA) file from https://api.hypersecuredbaas.ibm.com/cert.pem, and copy it to an appropriate directory such as **/etc/ssl/certs/**.

3. Obtain an access token and a user ID using the GET /auth/token operation:

   ```javascript
      curl -X GET -H "accept: application/json" -H "api_key: icGVY1*** ***UdfcIg4kzE" https://mgmt06.hypersecuredbaas.ibm.com:20000/api/ /auth/token
   ```
   {: codeblock}

  This operation returns an access token and a user ID similar to this example:

  <pre>
    {
      "access_token":"eyJraWQiOiIyMDE3MT*** ***3V4pMYrOvMniLA",
      "user_id":"e9433*** ***b188"
     } 
   </pre>
	
4. Save the values of the access token and the user ID for future use.
