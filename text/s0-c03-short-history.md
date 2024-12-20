<!--
SPDX-FileCopyrightText: 2008 Scott Chacon <schacon@gmail.com>

SPDX-License-Identifier: CC-BY-SA-3.0
-->

## A Short History of Git

The Git project started
with Linus Torvalds scratching the very serious itch of needing a fast,
efficient and massively distributed source code management system
for Linux kernel development.

The kernel team had moved from a patch emailing system
to the proprietary BitKeeper SCM in 2002.
That ended in April 2005 when BitMover stopped providing a free version of its tool
to the open source community,
because they felt some developers had reverse engineered it
in violation of the license.

Since Linus had (and still has)
a passionate dislike of just about all existing source code management systems,
he decided to write his own.
Thus,
in April of 2005,
Git was born.
A few months later,
in July,
maintenance was turned over to Junio Hamano,
who has maintained the project ever since.

> **NOTE** \
"I'm an egotistical bastard,
and I name all my projects after myself.
First Linux,
now git." - Linus

Git started out as a collection of lower level functions
used in various combinations by shell and perl scripts.
Recently (since 1.0),
more and more of the scripts have been re-written in C
(referred to as built-ins),
increasing portability and speed.

Though originally used for just the Linux kernel,
the Git project spread rapidly,
and quickly became used to manage a number of other Linux projects,
such as the X.org,
Mesa3D,
Wine,
Fedora and Samba projects.
Recently it has begun to spread outside the Linux world
to manage projects such as Rubinius,
Merb,
Ruby on Rails,
Nu,
Io and many more major open source projects.
