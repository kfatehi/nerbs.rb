If you're on Mac, use this https://github.com/nerves-project/homebrew-nerves

---

# nerbs

A ruby script for doing nerves development (code editing and firmware updates) from their Mac.

It works using `ssh` and `rsync` against a networked linux host with the nerves sdk already on it.

You need [fwup](https://github.com/nerves-project/nerves-sdk) to run the `burn-complete` and `burn-upgrade` tasks.

## Install

Execute `nerbs.rb` from your nerves project directory.

**It uses the `USER` and `NERVES_SDK_HOST` environment variables to compose `rsync` and `ssh` targets, so make sure they are set**

You can symlink it

    chmod a+x nerbs.rb && ln -s $PWD/nerbs.rb /usr/local/bin/nerbs

## Tasks

* build - shorthand for push, compile, and pull
* push - uploads project source code with `rsync`
* compile - pushes source code, sources sdk, and compiles remotely with `ssh`
* pull - downloads the `_images` directory
* burn-complete - writes the complete image with `fwup`
* burn-upgrade - writes the upgrade image with `fwup`
