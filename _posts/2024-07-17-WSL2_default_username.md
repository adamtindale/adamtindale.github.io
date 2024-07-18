---
title: "WSL2 - Changing the default username"
date: 2024-07-17 19:30
categories: [wsl] # always lowercase, comma space seperated
tags: [wsl] # always lowercase, comma seperated
---

> This guide is using Ubuntu as the distribution
{: .prompt-tip } 

If you have already setup your Ubuntu user and would like to change the default, this is how to do it:

First, open Ubuntu and create the user that matches your default:

```bash
sudo adduser example-user
```

Then add the newly created user into the sudo group:

```bash
sudo usermod -a -G sudo example-user
```

Go back to CMD or PowerShell and find the instance name

```powershell
wsl -l

Windows System for Linux Distributions:
Ubuntu (Default)
```

Then use the instance name and change the default user

```powershell
Ubuntu config --default-user example-user
```

This will prompt a restart of Ubuntu that you still have open.

All done!
