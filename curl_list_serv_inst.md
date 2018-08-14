---

copyright:
  years: 2018
lastupdated: "2018-08-09"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}


# Listing a service instance

To list all the services in your account, use this command:

```javascript
curl -X GET -H "Content-Type: application/json" -H "Accept: application/json" -H "Authorization: Bearer eyJraWQiOiIyMDE3MT*** ***3V4pMYrOvMniLA" "https://resource-controller.ng.bluemix.net/v1/resource_instances?resource_plan_id=5bb4a184-fcb3-45ee-
876a-f28f62a59c29"
```
{: codeblock}

The system returns a JSON object containing all the DBaaS service instances in your account.

