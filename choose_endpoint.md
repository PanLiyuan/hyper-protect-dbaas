---

copyright:
  years: 2017, 2019
lastupdated: "2019-02-21"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}


# Choosing a service endpoint to log in to

IBM Cloud provides many service endpoints in various geographical regions that you can log in to. 
To find a service endpoint near your geographical location, use the **ibmcloud regions** command as shown in this example:

<pre><code class="hljs">~$ ibmcloud regions
Listing regions...

Name       Geolocation      Customer   Deployment   Type
au-syd     Sydney           IBM        Production   public
jp-tok     AP North
eu-de      Germany          IBM        Production   public
eu-gb      United Kingdom   IBM        Production   public
us-east    US East          IBM        Production   public
us-south   US South         IBM        Production   public

</code></pre>

**Note:** Currently, {{site.data.keyword.cloud_notm}} Hyper Protect DBaaS is supported only on the **us-east** region.

To log in to an IBM Cloud service endpoint, follow these steps:

1. Enter the **ibmcloud login** command, indicating that you are using Single Sign-On (SSO) and specifying the URL of the endpoint you want to log in to, as shown in this example:

   <pre><code class="hljs">~$ ibmcloud login --sso -a https://api.ng.bluemix.net
      API endpoint: https://api.ng.bluemix.net
   </code></pre>
   
   The system displays a URL for a web page that provides you with a one-time passcode:
   
   <pre><code class="hljs">One Time Code (Get one at https://iam.au-syd.bluemix.net/identity/passcode)
   </code></pre>   
 
2. Copy the URL from your system console and paste it into your web browser.
 
   The system displays the "IBM Cloud One time passcode" page.

3. Copy the passcode from the web page and paste it into your system console command line. 

   The passcode is not displayed in the command line. When the password is authenticated, you receive an **OK** message indicating that you are logged in, as shown in this example:

   <pre><code class="hljs">One Time Code (Get one at https://iam.au-syd.bluemix.net/identity/passcode)>
   Authenticating...
   OK
   </code></pre>

For more information about the **ibmcloud login** command parameters, see "bluemix login" at this URL:

https://cloud.ibm.com/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#bluemix_login

**Note:** When you use {{site.data.keyword.cloud_notm}} Hyper Protect DBaaS, you might need to create spaces in more than one region 
and switch between regions by using the **ibmcloud target** command. For more information, see 
"Creating organizations and spaces" (https://cloud.ibm.com/docs/account?topic=account-orgsspacesusers#orgsspacesusers) 
and "bluemix target" (https://cloud.ibm.com/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#bluemix_target).






