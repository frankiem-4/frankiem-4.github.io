---
layout: page 
title: Snippets 

---
# Powershell

### Turn firewalls on and off
<code>
Set-NetFirewallProfile -Profile Domain,Public,Private -Enabled True
</code>
or if ypur on an older version of windows use the following
<code>
netsh advfirewall set allprofiles state on
</code>
