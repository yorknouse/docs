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

