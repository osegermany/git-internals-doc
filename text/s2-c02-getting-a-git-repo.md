<!--
SPDX-FileCopyrightText: 2008 Geoffrey Grosenbach <boss@topfunky.com>
SPDX-FileCopyrightText: 2008 Scott Chacon <schacon@gmail.com>

SPDX-License-Identifier: CC-BY-SA-3.0
-->

## Getting a Git Repository

There are two major ways you will get a Git repository -
you will either clone an existing project,
or you will initialize a new one.

### New Repositories

To create a new Git repository somewhere,
simply go to the directory you want to add version control to and type:

```shell
git init
```

This will create a `.git` directory in your current working directory
that is entirely empty.
If you have existing files you want to add to your new repository,
type:

```shell
git add .
git commit -m 'my first commit'
```

This will add all of your current files into your new repository
and index and then create your first commit object,
pointing your new `master` branch to it.
Congratulations,
you have now added your source code to Git.

- [git init](https://mirrors.edge.kernel.org/pub/software/scm/git/docs/git-init.html)
- [git commit](https://mirrors.edge.kernel.org/pub/software/scm/git/docs/git-commit.html)
- [git add](https://mirrors.edge.kernel.org/pub/software/scm/git/docs/git-add.html)

### Cloning a Repository

Many times you will be *cloning* a repository,
however.
This means that you are creating a complete copy of another repo,
including all of its history and published branches.

> **NOTE** \
A clone is,
for all intents and purposes,
a full backup.
If the server that you cloned from has a hard disk failure
or something equally catastrophic,
you can basically take any of the clones
and stick it back up there when the server is restored
without anyone really the worse for wear.

In order to do this,
you simply need a URL that has a Git repository hosted there,
which can be over HTTP,
HTTPS,
SSH or the special *git* protocol.
We will use the public hosted repository
of the simple library I mentioned at the beginning of the book.

```shell
git clone git://github.com/schacon/simplegit.git
```

This will by default create a new directory called `simplegit`
and do an initial checkout of the `master` branch.
If you want to put it in a different directory than the name of the project,
you can specify that on the command line,
too.

```shell
git clone git://github.com/schacon/simplegit.git my_directory
```

- [git clone](https://mirrors.edge.kernel.org/pub/software/scm/git/docs/git-clone.html)
