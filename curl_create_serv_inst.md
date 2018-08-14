---

copyright:
  years: 2018
lastupdated: "2018-08-10"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}


# Creating a service instance

To create a service instance using the RESTful API, follow these instructions:

1. Determine the ID of the resource group in which you want to create the new service instance.

   a. To list all resource groups in your IBM Cloud account, invoke the GET RESTful API as shown in this example:
   
      ```javascript
       curl -X GET --header 'Content-Type: application/x-www-form-urlencoded' --header 'Accept: application/json' --header 'Authorization:   Bearer eyJraWQiOiIyMDE3MT*** ***3V4pMYrOvMniLA' https://resource-manager.bluemix.net/v1/resource_groups 
      ```
      {: codeblock}

     Where the string following **Authorization: Bearer** specifies the previously-obtained access token; see [Setting up authentication to use IBM Cloud APIs](../../../docs/services/hyper-protect-dbaas/icloud_auth.html). (**Note:** If the access token has expired, return to those instructions and request a new token.)

     The system lists one or more resource groups, as shown in this example:
     
     <pre><code class="hljs">{
     "resources":[
       {
         "id":"6ae3***738cd",
         "crn":"crn:v1:bluemix:public:resource-controller::a/925***520::resource-group:6ae***38cd",
         "account_id":"925***520",
         "name":"default",
         "state":"ACTIVE",
         "default":true,
         … …
         "created_at":"2017-09-17T07:19:38.889Z","updated_at":"2017-09-17T07:19:38.889Z"
         },
         … …
       ]
      }
     </code></pre>
   
   b. Make note of the ID of the resource group in which you want to create a DBaaS service instance, and proceed to the next step.

2. To create a DBaaS service instance in the desired resource group, invoke the POST RESTful API as shown in this example:
  
   ```javascript
      curl -X POST -H "Content-Type: application/json" -H "Accept: application/json" -H "Authorization: Bearer eyJraWQiOiIyMDE3MT*** ***3V4pMYrOvMniLA" --data '{"name":"CreatedByRESTfulAPI01", "region_id": "us-south", "resource_group_id": "6ae3***738cd", "resource_plan_id": "5bb4a184-fcb3-45ee-876a-f28f62a59c29", "parameters":{"name":"RESTfulAPITest01", "admin_name":"admin", "password":"Pass1234", "confirm_password":"Pass1234","db_type":"MongoDB","license_agree":["agreed"]}}' https://resource-controller.ng.bluemix.net/v1/resource_instances 
     ```
   {: codeblock}

   Where the parameters have the following definitions:
   
| Parameter           | Definition                                                    |
| :---------------    | :------------------------------------------------------------- |  
| Authorization:      | The access token.  |
| name:               | The name of the service instance to be created. This name will be shown in the service list. |
| region_id:          | The region in which you want to create the DBaaS service instance. (**Note:** Currently, the only valid values are "eu-gb" and "us-south".) |
| resource_group_id:  | The ID of the resource group in which the instance is to be created. |
| resource_plan_id:   | The resource service plan to be used. For the DBaaS “Lite” service plan, the only valid value is **"5bb4a184-fcb3-45ee-876a-f28f62a59c29"**. |
| parameters:         | A valid JSON string containing the items in the following table. |  
  
| "parameters" item   | Definition |
| :--------------- |  :------------------------------------------------------------- |
| name:            | The name of the cluster. This name will be shown in the cluster dashboard. |
| admin_name:      | The administrator's user name. |
| password:         | The administrator's password. It must contain at least 8 characters, at least 1 upper case letter, at least 1 lower case letter, at least 1 numeric; and it cannot equal the *admin_name*. |
| confirm_password: | The same password. |
| db_type:          | The type of database service to be created. (**Note:** Currently only **"MongoDB"** and **"PostgreSQL"** are supported.) |
| license_agree:    | **"agreed"**. This indicates acceptance of the license agreement and is required in order to proceed. |
   
   The system returns output similar to this example:
   
   <pre><code class="hljs">{
     "id":"crn:v1:bluemix:public:hypersecuredbaas:us-south:a/925***520:b13ead17-638f-4028-9aa6-6eeacd7862e8::",
     "guid": "b13ead17-638f-4028-9aa6-6eeacd7862e8",
     "url": "/v1/resource_instances/crn%3Av1%3Abluemix%3Apublic%3Ahypersecuredbaas%3Aus-south%3Aa%2F925***520%3Ab13ead17-638f-4028-9aa6-6eeacd7862e8%3A%3A",
     "created_at": "2018-06-05T06:18:40.355483888Z",
     "updated_at": null,
     "deleted_at": null,
     "name": "CreatedByRESTfulAPI01",
     "region_id": "us-south",
     "account_id": "925d4bfc976e9cf539bfacda0e04a520",
     
   … …
     "migrated": false
   }
   </code></pre>
   
   For future reference, make note of the **"id"** value assigned to the service instance, 
   as this is how it must be specified when invoking other RESTful APIs.

For more details, see https://console.bluemix.net/apidocs/700-resource-controller-api.

