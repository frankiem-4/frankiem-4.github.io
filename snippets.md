---
layout: page 
title: Snippets 

---

# Snippets of Code 
Useful pieces of code that I use often, hopefully these might be of use to others.



# Powershell
- Code that works in powershell


## Turn firewalls on and off
<code>
Set-NetFirewallProfile -Profile Domain,Public,Private -Enabled True
or
netsh advfirewall set allprofiles state on
</code>
