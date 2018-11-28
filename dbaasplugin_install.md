---

copyright:
  years: 2018
lastupdated: "2018-11-26"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}


# Installing the DBaaS CLI plug-in

To access a complete set of DBaaS commands when using the IBM Cloud CLI, 
you must install the following components 
(see [Instructions](#dbaas_cli_instr)):

- Python runtime (2.7.15 is recommended; 3.*x* is *not* supported)
- Python Pip package management system
- Python Requests library
- DBaaS CLI plug-in

## Instructions for installing the DBaaS CLI components (by operating system)
{: #dbaas_cli_instr}

- [On Linux](#dbaas_cli_linux)
- [On MacOS](#dbaas_cli_macos)
- [On Windows](#dbaas_cli_windows)

### On Linux:
{: #dbaas_cli_linux}

1. Most Linux distributions have Python and Pip preinstalled. If yours does not, use these commands to install them:
   
   <pre><code class="hljs">sudo apt-get install python python2.7 python-dev
   sudo apt-get install python-pip</code></pre>
  
2. To install the Python Requests library, use this command:

   <pre><code class="hljs">sudo pip install requests</code></pre>

3. To install the DBaaS CLI plug-in, use this command:

   <pre><code class="hljs">ibmcloud plugin install dbaas-cli</code></pre>

4. To confirm that the DBaaS CLI plug-in has been installed correctly, use this command:

   <pre><code class="hljs">ibmcloud</pre></code>

   The system displays **dbaas** in the list of available commands.

### On MacOS:
{: #dbaas_cli_macos}

1. If you do not already have Python, download and install it by following these instructions:

    a. Go to the Python website at this URL: https://www.python.org/downloads/release/python-2715/

    b. Select the appropriate MacOS installer, download it, and run it. The installation should include Pip.
    
2. To install the Python Requests library, use this command:

   <pre><code class="hljs">sudo pip install requests</code></pre>

3. To install the DBaaS CLI plug-in, use this command:

   <pre><code class="hljs">ibmcloud plugin install dbaas-cli</code></pre> 

4. To confirm that the DBaaS CLI plug-in has been installed correctly, use this command:

   <pre><code class="hljs">ibmcloud</pre></code>

   The system displays **dbaas** in the list of available commands.

### On Windows:
{: #dbaas_cli_windows}

**Note:** Only the x86_64 version of Windows is supported.
     
1. If you do not already have Python, download and install it by following these instructions:

    a. Go to the Python website at this URL: https://www.python.org/downloads/release/python-2715/

    b. Select the **Windows x86-64 MSI** installer, download it, and run it.
    
    c. On the **Customize Python** menu of the **Python Setup** wizard, specify: **pip Will be installed on local hard disk drive**
 
2. After installing Python, use your Windows **Edit System Variable** dialog to 
   append the following values to the existing **Path** variable value:

   <pre><code>C:\Python27;C:\Python27\Scripts</code></pre>

3. To install the Python Requests library, open the **Command Prompt** window and enter this command:

   <pre><code class="hljs">pip install requests</code></pre>

4. To install the DBaaS CLI plug-in, use this command:

   <pre><code class="hljs">ibmcloud plugin install dbaas-cli</code></pre> 

5. To confirm that the DBaaS CLI plug-in has been installed correctly, use this command:

   <pre><code class="hljs">ibmcloud</pre></code>

   The system displays **dbaas** in the list of available commands.
