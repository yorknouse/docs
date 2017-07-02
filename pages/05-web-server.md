---
title: Web server
layout: page
order: 2
---

We have a web server.
It is currently supplied by Digital Ocean,
because of [the GitHub Student Developer Pack's $100 free credit](https://education.github.com/pack).
We have used Linode in the past, but are moving to using a Linux VM from IT Services.

## Nginx

Nginx is the web server program that runs on our web server. The configuration files are in `/etc/nginx/`. Some of the most important are in fact symlinks to files in `/var/www/nouse/config/`, so should be [edited via GitHub](https://github.com/yorknouse/nouse/tree/master/config).

Logs are in `/var/log/nginx/`. `error.log` is useful:

    sudo less /var/logs/error.log

## Varnish

[Varnish](https://www.varnish-cache.org/) sits in front of Nginx on port 80.
It caches requests and makes pages load faster.
Configuration is in `/etc/varnish/default.vcl` and `/etc/defaults/varnish`.

We use a WordPress plugin to "purge" relevant parts of the whenever content is published or updated and comments are published.
After deploying changes to the source code, if you want the changes to be visible immediately, you can do a "manual purge" either from the WordPress admin panel or by SSHing in and using `varnishadm`:

`sudo varnishadm "ban req.url ~ ."`
: Purges the whole cache. Slightly better than restarting Varnish, but still dramatic

`sudo varnishadm "ban req.url ~ .css"`
: Purges all URLs containing `.css`

### Ideas

We could improve the deployment scripts to do more purging automatically. But it's nice to have a bit of leeway if one breaks something.

We should use Edge Side Includes to allow updating common bits of pages (like headers and footers) more easily.
An alternative approach is to use JavaScript to load stuff -- non-essentials like Most Read lists can load after the main content (we already do this with comment voting, sidebar adverts, and Roses and College Varsity live score tables).

## Node.js

There are some apps which run using [Node.js](https://nodejs.org).  These can be a bit temperamental at times.

### Ideas

Viddyprinter could do with some extra admin features to make managing events a bit easier.
It would also be nice to allow for in game scores to be better configurable with different sports having different profiles (but that would take some work)

Account is horrible and isn't really fit for it's current purpose (and never totally was).  A better user management system that integrates into other services we have (Google Apps, Slack, WordPress) would be a really nice addition.
