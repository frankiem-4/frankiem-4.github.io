---
layout: page 
title: Snippets 

---
# Powershell

### Turn firewalls on and off
<code>
Set-NetFirewallProfile -Profile Domain,Public,Private -Enabled True
</code>
or if you're on an older version of windows use the following
<code>
netsh advfirewall set allprofiles state on
</code>



### Install telnet client from POSH
<pre><code>
Import-Module servermanager
Add-WindowsFeature telnet-client
</code>i</pre>
