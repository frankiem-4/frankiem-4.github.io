---
layout: post
title: "MBR2GPT Tool"
date: 2017-06-02 19:00:00
tags: 
---
# MBR2GPT Tool

Short story then onto the goods.

I was setting up a user (prior OS X user) with a new laptop. For whatever reason the laptop was setup to BIOS instead of UEFI when 
I install Windows 10 Pro. It installed and created the Master Boot Record. So when I went to encrypt the drive using Bitlocker, I 
found that it wouldn't work because UEFI is required for secure boot to work. I did a little digging and found that in 
Windows 10 build 1703 a tool called MBR2GPT was available. Usually these things are difficult, but I didn't want to have to reinstall
since the user was already completely setup and customized. Turns out it was pretty easy:

*Highly suggest backing up any important files just incase this doesn't go well*
From an elevated CMD.exe
<code>MBR2GPT /validate /allowFullOS</code>
This should validate that you are ready to go, and let you know if you aren't

Then once that is working properly run
<code>MBR2GPT /convert /allowFullOS</code>

After this completes (shouldn't take very long), restart the computer and in the BIOS change over the UEFI mode. Then start the PC.
That's it! Was super simple.

<pre><code>
C:\> mbr2gpt /?

Converts a disk from MBR to GPT partitioning without modifying or deleting data on the disk.

MBR2GPT.exe /validate|convert [/disk:<diskNumber>] [/logs:<logDirectory>] [/map:<source>=<destination>] [/allowFullOS]

Where:

 /validate
         - Validates that the selected disk can be converted
           without performing the actual conversion.

 /convert
         - Validates that the selected disk can be converted
           and performs the actual conversion.

 /disk:<diskNumber>
         - Specifies the disk number of the disk to be processed.
           If not specified, the system disk is processed.

 /logs:<logDirectory>
         - Specifies the directory for logging. By default logs
           are created in the %windir% directory.

 /map:<source>=<destination>
         - Specifies the GPT partition type to be used for a
           given MBR partition type not recognized by Windows.
           Multiple /map switches are allowed.

 /allowFullOS
         - Allows the tool to be used from the full Windows
           environment. By default, this tool can only be used
           from the Windows Preinstallation Environment.
</pre></code>

More information can be found here:
https://docs.microsoft.com/en-us/windows/deployment/mbr-to-gpt

- FM
