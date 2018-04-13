---

copyright:
  years: 2017
lastupdated: "2018-03-13"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}


# Choose a service endpoint to log into

IBM Cloud provides many service endpoints in various geographical regions that you can log into. 
To find a service endpoint near your geographical location, use the **bx regions** command as shown in this example:

<pre><code class="hljs">~$ bx regions
Listing Bluemix regions...

Name       Geolocation      Customer   Deployment   Domain                CF API Endpoint                   Type
en-de      Germany          IBM        Production   eu-de.bluemix.net     https://api.eu-de.bluemix.net     public
au-syd     Sydney           IBM        Production   au-syd.bluemix.net    http://api.au-syd.bluemix.net     public
us-east    US East          IBM        Production   us-east.bluemix.net   https://api.us-east.bluemix.net   public
us-south   US South         IBM        Production   ng.bluemix.net        https://api.ng.bluemix.net        public
en-gb      United Kingdom   IBM        Production   eu-gb.bluemix.net     https://api.eu-gb.bluemix.net     public
</code></pre>

**Note:** Currently {{site.data.keyword.cloud_notm}} Hyper Protect DBaaS is supported only on the **us-south** and **en-gb** regions.

To log into an IBM Cloud service endpoint, follow these steps:

1. Enter the **bx login** command, indicating that you are using Single Sign-On (SSO) and specifying the URL of the endpoint you wish to log into, as shown in this example:

   <pre><code class="hljs">~$ bx login --sso -a https://api.ng.bluemix.net
   API endpoint: https://api.ng.bluemix.net

   One Time Code (Get one at https://iam.au-syd.bluemix.net/identity/passcode)
   </code></pre>
   
   As shown, the system displays a URL for a web page that will provide you with a one-time passcode.
 
2. Copy the URL from your system console and paste it into your web browser.
 
   The system displays the "IBM Cloud One time passcode" page.

3. Copy the passcode from the web page and paste it into your system console command line. 

   The passcode will not be displayed in the command line; 
   however, once the password has been authenticated, you will receive an 
   **OK** message indicating that you are logged in, as shown in this example:

   <pre><code class="hljs">One Time Code (Get one at https://iam.au-syd.bluemix.net/identity/passcode)>
   Authenticating...
   OK
   </code></pre>

For more information about the **bx login** command parameters, see "bluemix login" at this URL:

(https://console.bluemix.net/docs/cli/reference/bluemix_cli/bx_cli.html#bluemix_login)

**Note:** When using {{site.data.keyword.cloud_notm}} Hyper Protect DBaaS, you might need to create spaces in more than one region 
and switch between regions using the **bx target** command. For details about how to do this, see 
"Creating organizations and spaces" (https://console.bluemix.net/docs/account/orgs_spaces.html#orgsspacesusers) 
and "bluemix target" (https://console.bluemix.net/docs/cli/reference/bluemix_cli/bx_cli.html#bluemix_target).






