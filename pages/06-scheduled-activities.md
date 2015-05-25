---
title: Scheduled activities
layout: page
---

Some [Cron](https://en.wikipedia.org/wiki/Cron) jobs run regularly, under the `www-data` user.

You can read `www-data`'s _crontab_:

    sudo crontab -l -uwww-data

...and edit it:

    sudo crontab -e -uwww-data

## Examples

Some PHP scripts that run via [WP-CLI](http://wp-cli.org/):

`cd /var/www/nouse/wp-content/scripts; /usr/local/bin/wp eval-file fix-missed-schedule.php`
: Publishes any scheduled posts, every 5 minutes

`cd /var/www/nouse/wp-content/scripts; /usr/local/bin/wp eval-file update-counts.php`
: Updates the pageviews in the WordPress admin panel, and the Most Read lists on the site

Some other scripts and commands:

`python ~/scripts/backup-best.py`
: This is run weekly during the Fantasy Football season, to generate the "team of the week" on the front page. Outside of season, it adds an empty team to the database, which we do not want, so we comment out the line in the crontab. (It would be better to fix the script so that it won't matter)

`/var/www/scripts/nouse-backup-wp`
: Backs up the WordPress MySQL database to the `/var/wwww/backup/` folder. The backup is compressed using `gzip` with the `--rsyncable` flag

`/var/www/scripts/nouse-backup-wp`
: Backs up the Fantasy Football MySQL database...

`mutt -s "Database backup" -a /var/www/backup/fantasy_football_backup.sql.gz -- tech@nouse.co.uk`
: Emails the database backup to someone as an attachment. The WordPress backup is probably too big to email, and the Fantasy Football database doesn't change outside of the season, so this is commented out most of the time
