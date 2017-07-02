---
title: SSL
layout: page
---

## Server

The server currently uses a certificate to communicate with the CDN only and as such will not work in peoples browsers as it is not trusted.  [Let's Encyrpt](https://letsencrypt.org/) is the obvious solution going forward.

## CDN

Traffic to our server is routed via the CloudFlare network to reduce demand on the server and offer some DDoS protections.  It also issues the SSL certificiates people will see in their browsers.  An entire website could be ([and is](https://support.cloudflare.com/hc/en-us)) dedicated to configuring the CDN correctly.  So long as the main site records aren't messed about with there is some scope for trial and error to get the right configurations when making changes.

As we use the free CDN remember that we only have one option to clear the CDN which is to remove **everything** from the CDN, so it's best to make sure things don't get out there that shouldn't be in the first place.
