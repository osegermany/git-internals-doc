<!--
SPDX-FileCopyrightText: 2008 Geoffrey Grosenbach <boss@topfunky.com>
SPDX-FileCopyrightText: 2008 Scott Chacon <schacon@gmail.com>

SPDX-License-Identifier: CC-BY-SA-3.0
-->

## Hosted Repositories

If you don't want to deal with setting up and maintaining your own server
for your git repository,
you can use one of the growing number of public Git hosted servers.

I will focus on some interesting features
of a commercial service called [GitHub](https://github.com) here,
but there is also an open source project
called [CodeBerg](https://codeberg.org/) -
using the [Gitea](https://gitea.io/) software -
that has many of the same features.

> **NOTE** \
One of the compelling features of GitHub
is the ability to create a private repository
and share it with only a few developers.
However,
the complete source to Gitorious is available as a Ruby on Rails application.
It could be modified to run on your company's server
if your project needs to remain private.

GitHub hosts many popular projects featured in the PeepCode series,
including [Ruby on Rails](https://github.com/rails/rails/),
[Merb](https://github.com/wycats/merb-core/),
[RSpec](https://github.com/dchelimsky/rspec/),
and [Capistrano](https://github.com/capistrano/capistrano/).

### GitHub

GitHub is interesting as a source code hosting service
because it includes some social networking features,
which is not what most people imagine
when they think of hosting source code.

You can follow friends,
other developers,
or just individual projects.
You then subscribe to a single Atom feed
and are kept up to date on what all those projects and people are doing,
code-wise.

![Custom GitHub home page with your projects](../artwork/screenshots/github1.png)

More interestingly,
you can publicly fork a project to get your own copy of it.
GitHub is unique in concept
in that it is really centered around individuals rather than projects.
For instance,
if you want to follow or work on Merb,
you would follow or fork wycats's Merb.
There is really no *official* Merb page in GitHub.
It's simply that wycats is known to be the blessed repository
by the Merb project.

> **NOTE** \
In fact,
Rails itself has at one point been forked
and significantly enhanced by Ezra Zygmuntowicz.
In other contexts this would be a bold divisive gesture,
but with Git it's common practice.

You could just as easily follow and fork
someone else's repository of the project.
An interesting example of this is the [git-wiki](
https://github.com/sr/git-wiki) project,
which was started by a user named `sr`,
then was forked and greatly modified by `al3x`.
`sr` wanted to keep the project simple,
so now there are two major versions of the project.
I have a checkout of the project and remotes added for each one,
so I could work on and contribute to either.

![Project network visualization](../artwork/screenshots/github-network.png)

Let's say there is a popular feature request
that is either not completed or not accepted
by the main project maintainer.
You can very easily fork the project
and keep your patch or patches up to date with the head
on a regular basis
and people can pull from yours instead.
Perhaps enough demand builds up
or enough testing is done from all these users
that the patch is accepted.
You can then delete your fork
and revert to the original project head.

This will also really change patch submission for large projects.
Instead of emailing patches around,
you can fork the project,
add your patch
and submit a pull request for your branch
with the fix to one of the core members
or through the ticketing system.
A member of the core team can add you as a remote easily,
create a new testing branch,
merge in or rebase your branch,
test and accept or reject.
If your patch is ignored
or the team doesn't have time to deal with it yet,
it's easy to keep up to date
by continually rebasing and re-sending the pull requests
until it's either rejected or accepted.
It doesn't just go stale until it's difficult to apply the patch anymore.

Services like GitHub and an increased adoption of distributed SCM systems
will dramatically change open source development workflows
on teams of all sizes,
in addition to changing the way individual developers work.
