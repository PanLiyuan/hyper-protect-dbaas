---

copyright:
  years: 2017, 2018
lastupdated: "2018-04-23"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}


# Running the command-line interface

## Procedure
{: #running_cli_proc}

To enter a CLI command:

<ol>
<li>Set the environment variables.
<pre><code class="hljs"># source openrc
</code></pre>
</li>
<li>Use the **dmclient** command followed by the CLI command and its parameters.
<pre><code class="hljs"># ./dmclient <*cli-command*> <*parameter-list*>
</code></pre>
<p>See **Reference > Command-line interface** for a list of available CLI
commands and their parameters.</p>
</li>
</ol>


## Example
{: #running_cli_xmp}

* The **help** CLI command displays a list of available CLI commands:
```
# source openrc
# ./dmclient help
```

* To create a database cluster, issue:
```
# source openrc
# ./dmclient --accept-license cluster-create myClusterName user password
```
