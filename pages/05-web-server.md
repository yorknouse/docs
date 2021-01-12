---
title: Web server
layout: page
order: 2
---

The University provides us with a Virtual Machine (yusunouse01.york.ac.uk) which is exposed to the web to allow it to be accessed by Cloudflare.

| Item | Details |
|---|---|
| Hostname | yusunouse01.york.ac.uk | 
| OS | Linux Ubuntu 20.04 | 
| Memory | 4GB | 
| CPU | 2CPU | 
| Storage | 30GB - but really doesn't need much as all it stores is the database |
| Network | Gigabit - seems to get about 650 Mbit/s down and 465 Mbit/s up |

The University back it up for 90 days - I don't really know what this means, and so we also back up the Database separately.
The code on the machine is just a copy from the Github, it shouldn't even be edited locally anyway so that's not backed up by us or anything. 

To access it:
- Ensure you've been added by IT services
- Are using the VPN
- Have setup the SSH key on your client