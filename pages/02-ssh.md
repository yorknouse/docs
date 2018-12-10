---
title: SSH
layout: page
---

Remote login to the servers and office iMacs is done through SSH.

## Adding accounts

To add a user called, for example, `greg`:

    $ sudo adduser greg

Require a change of password in 0 days' time:

    $ sudo chage -d 0 greg

Allow `greg` to use the `sudo` command:

    $ sudo adduser greg sudo

To let `greg` log in via SSH, add `greg`'s public key to `/home/greg/.ssh/authorized_keys`, and then:

    $ sudo chown -R greg.greg /home/greg/.ssh
    $ sudo chmod 700 /home/greg/.ssh
    $ sudo chmod 600 /home/greg/.ssh/authorized_keys

## Logging in

If you’re using Linux or Mac OS X then an SSH client is built in:

    $ ssh username@nouse.co.uk

If you’re using Windows then one way to log in is using the PuTTY client, which you can get as a standalone application or installer from its website, and which is also installed on all PCs on campus.

If you lose your SSH keys, the <del>Lish Ajax Console in the [Linode Manager](https://manager.linode.com/session/index) (under Remote Access)</del> allows password authentication.

## Using the command line

This isn't really the place for a full-blown tutorial.

## Saving keystrokes

On Linux (and probably OS X) if you type `ssh nouse.co.uk` it will by default try to use your local username. But I'm `josh` on my computer and `jclg500` on the Nouse server so I have to type `jclg500` right?

Wrong. I have put this in my local `~/ssh/config` file:

    Host nouse.co.uk
    User jclg500

Even better, I can do this:

    Host n
    User jclg500
    HostName nouse.co.uk

So I only need to type `ssh n`.

## SSH locations available

### Office Macs

Information on the names and usernames is given with other information about the [office](office.html).
