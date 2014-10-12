---
title: Version control
layout: page
---

Most of the website lives in some [Git][git] repositories.

We have [a GitHub organisation][gh] which you should be invited to.
We are allowed 10 private repositories for free, [because we are students][gh-student] (be sure to [upgrade your individual account][gh-student-form] too), but it is nice to make as many repositories public as possible.

Our friends at [URY][ury] and [YSTV][ystv] are pioneers.

We also have [a Bitbucket account][bb], but no longer use it.

[git]: http://git-scm.com/ "A distributed version control system"
[gh]: https://github.com/yorknouse
[gh-student]: https://education.github.com/
[gh-student-form]: https://education.github.com/discount_requests/new
[ury]: https://github.com/universityradioyork
[ystv]: https://github.com/ystv
[bb]: https://bitbucket.org/yorknouse

## Git clients

Some of us use Git from the command line.
There are are plenty of [tutorials](https://try.github.io/) floating around the internet.

Otherwise, GitHub [for Mac](https://mac.github.com) and [for Windows](https://windows.github.com) are good and free, as is [SourceTree](http://www.sourcetreeapp.com/).

## Hygeine

There are plenty of recommendations about Git "workflows" online.

Commits to our `master` branch can be expected to go live as soon as they are pushed (see [deployment](#deployment) below).
But you should commit and push regularly -- so commit to a branch other than `master`, and merge your changes into `master` when you're ready.

## Deployment

Most of the repositories on GitHub have [Webhooks][webhooks] set up.
When you push to GitHub, it will send a request to deploy.nouse.co.uk.
Our server will then pull any changes from the `master` branch, and write some information to a log.

### Manual deployment

When the server pulls from GitHub, `git` is run as the `www-data` user.
So relevant directories need to be [owned][chown] by `www-data`.
(This ownership is also important for WordPress uploads to the `/wp-content/article_images/body/` folder.)

When you are `ssh`ed into the server, this useful command will let you take on the `www-data` user's environment, and edit files to your heart's content:

    sudo -iuwww-data

(You can similarly become `root` by running `sudo bash`.)

When you're finished, you can return to your own environment by pressing <kbd>Ctrl</kbd>+<kbd>D</kbd> or using the `exit` command.

[webhooks]: https://developer.github.com/webhooks/
[chown]: http://en.wikipedia.org/wiki/Chown
