---
title: Web server
layout: page
order: 2
---

We have a web server.
It is currently Digital Ocean because of [the GitHub Student Developer Pack's $100 free credit](https://education.github.com/pack).
When that runs out, it may be worth asking YUSU about a university-supplied server (URY and YSTV both have some -- although their multimedia-heavy needs are greater than ours).
Otherwise, Linode are good (we used to use them, and the Digital Ocean hardware seems comparatively slower), or the excellent local company [Bytemark](https://www.bytemark.co.uk/) might be able to help (they currently sponsor HackSoc).

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

