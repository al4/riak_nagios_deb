riak_nagios debian packaging
============================

Simple debian package to install riak_nagios.

The build process does not work with the erlang/rebar included in jessie, you will probably need to install from source.

# Instructions
TL;DR:
clone the riak_nagios repo as a subdirectory of this repo, run debuild

## Environment

Ensure you have a gpg key setup and appropriate DEB variables in your environment, e.g:
```
export DEBEMAIL="alforbes@gumtree.com"
export DEBFULLNAME="Alex Forbes"
```

## Install erlang
Download debian package from https://www.erlang-solutions.com/downloads/download-erlang-otp

## Install rebar
From https://github.com/rebar/rebar/releases, I copied to /usr/local/bin.

## Install build dependencies
```
apt-get install build-essential devscripts git
```

## Merge this repo
Copy the contents of this repo over https://github.com/basho-labs/riak_nagios

## Edit the Makefile
TODO - this should be done with a patch, or debhelper override

Add 'escript' to the 'all:' line.

Also remove distclean if you're pre-building the dependencies (deps).

## Build the package
```
export REBAR_DEPS=
debuild
```
