<!--
SPDX-FileCopyrightText: 2008 Geoffrey Grosenbach <boss@topfunky.com>
SPDX-FileCopyrightText: 2008 Scott Chacon <schacon@gmail.com>

SPDX-License-Identifier: CC-BY-SA-3.0
-->

## Non-SCM Uses of Git

I keep saying that Git is primarily a content tracking toolkit
with SCM tools built on top of it.
So,
if it's not built specifically to be an SCM,
perhaps it would be useful to see some other examples
of things it might be good for.

This is a simple listing of some other tools
that have been built on Git internals
to demonstrate that an SCM is the bundled application,
but Git can also be a useful toolkit for any application
needing to track and manage slowly changing distributed trees of content.

### Peer to Peer Content Distribution Network

Imagine you are a retail chain or university campus
and have a network of digital signage displays
that play flash content advertisements or show campus news,
etc.
You have to get new content out to them every day or two,
which may consist of any combination of XML files,
images,
animations,
text and sound.

You need to build a content distribution framework
that will easily and efficiently transfer all the necessary content
to the machines on your network.
You need to constantly determine what content each machine has
and what it needs to have and transfer the difference
as efficiently as possible,
because networking to these units may be spotty.

It turns out that Git is an excellent solution to this problem.
You can simply check all the needed content into Git,
create a branch for each unit
and point that branch to the exact subtree of content it needs.
Then at some interval,
you have the unit fetch its branch.
If nothing has changed,
nothing happens - if content has changed somehow,
it gets only the files it does not already have in a delta compressed package
and then expands them locally.
Log and status files could even be transferred back by a push.

An example of a media company actually using this approach
is [Reactrix](https://reactrix.com/),
which also happens to be where I work.

> **NOTE** \
Somewhat interestingly,
Git being a good solution to this problem
is what exposed me to the tool in the first place.
We were using Git for content distribution on our network
since the 1.0 release back in 2005,
but using Perforce for version control internally.
It wasn't until nearly a year later
that we switched to actually using it to manage our source code.

### Distributed Document Oriented Database

Using Git as a backend for a document oriented database
could have some interesting applications.
Git provides a number of features such as replication,
searching with `grep`,
and full versioning history for free.

#### Distributed Wiki

Suppose we wanted to have a wiki for documentation on a project.
If we create a wiki that works on files,
we can simply write those files into a Git repository
and run a commit after every change.
This gives us good performance,
since it's just reading the content off the disk.
We also get full file version history and easy 'recently changed' data.
Searching is built in and we can edit the wiki offline.

The other cool feature we could use is the distributed nature of Git.
We could add other people on the project as remote repositories
and push to and fetch from them,
merging changes to write a book or documentation collaboratively.
We could branch to try out a re-write
and then either merge it in
or throw it away if we don't like it.
We could send a pull request to our colleagues
for them to try out the branch to preview it
before we decide whether to merge it in or not.

It's possible the entire wiki project could even live in a bare branch
(that is,
a branch with no common ancestors with any existing branch)
in the same repository as our project,
so clones can get the documentation as well,
without it muddying up our code tree.

See the [git-wiki](https://github.com/al3x/git-wiki/tree/master)
project for an example of this.

#### Distributed Issue Tracker

Another similar project might be a distributed ticketing system,
where all the tickets (bugs and features)
for a project could be stored in a Git repository,
worked on offline and transferred with a project.

Examples of projects trying to do this are
[git-bug](https://github.com/MichaelMure/git-bug)
(which is the most advanced as of 2023),
[Ditz](https://github.com/jashmenn/ditz) and my own
[TicGit](https://github.com/schacon/ticgit/wiki/).

### Backup Tool

Let's suppose
that you want to build something like a distributed Time Machine\[TM\] backup system
(Apple all rights reserved)
that efficiently packs up its backups
and transfers them to multiple machines.
I'm hoping by now
that you could see the benefits of using the Git toolkit to accomplish this,
but this particular problem is interesting
because of something that Git doesn't do,
which is permissions.
Git stores the mode of its content in the tree,
but it doesn't store any permissions data,
which means it's not good for backing up directories
in which permissions are important.
A good example would be the `/etc` directory on a Unix machine.

One project that has tackled this is [Gibak](
https://github.com/jaylevitt/gibak)
(TODO: This is old, maybe there is something more recent).
It implements a metastore in OCaml
and it's worth a look if this topic interests you.

> **NOTE** \
If you are interested in using Git in a non-standard way
and plan to use Ruby,
you might be interested in my [git gem](http://jointheconversation.org/rubygit/),
which provides an object oriented interface in Ruby to the Git tools,
including several of the lower level functions.
