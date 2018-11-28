---

copyright:
  years: 2018
lastupdated: "2018-11-20"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}


# Deleting a service instance

To delete a service instance, invoke the DELETE RESTful API, as shown in this example:

```javascript
curl -X DELETE -H "Content-Type: application/json" -H "Accept: application/json" -H "Authorization: Bearer eyJraWQiOiI*** ***ygSyuylLw" https://resource-controller.ng.bluemix.net/v1/resource_instances/crn%3Av1%3Abluemix%3Apublic%3Ahypersecuredbaas%3Aus-south%3Aa%2Fb036890f78cc6619a2755ad4214d0455%3A3737ea51-0a6c-46c6-bdee-1e82148a27fc%3A%3A
```
{: codeblock}

Where the string following https://resource-controller.ng.bluemix.net/v1/resource_instances/ specifies the bond ID of the service instance to be deleted. 
In this example, the string translates to this bond ID: 

<pre><code class="hljs">crn:v1:bluemix:public:hypersecuredbaas:us-south:a/b036890f78cc6619a2755ad4214d0455:3737ea51-0a6c-46c6-bdee-1e82148a27fc
</code></pre>	
