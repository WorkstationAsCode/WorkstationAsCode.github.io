---
title: Workstation As Code
---

:warning: Sorry but *Workstation As Code* is not yet an available tool!
It will, but for now, it's just ideation about how to convert my personal automation scripts into a more generic tool.

## Download & Install

_Not yet available!_

## Reasoning

### Why such a tool?

Because I want to:
* Not waste a huge amount of storage for all my computer backups when 99% of it is reliably
  available on the internet.
* Change my operating system or get back to the previous one easily.
* Install a lot of software and then get rid of them in the cleanest way.
* Be confident about what is running on my computer and master its configuration.

### What such a tool should do?
From an existing computer, I want to generate some human-readable code that describes the computer state:
* OS: kind (Ubuntu, Windows, macOS, ...), version, language, keyboard layout, timezone, computer name, other installation
  options...
* User: name, password, ssh and pgp keys, user-specific OS preferences...
* Installed software solutions and their non-default configurations
* Mounted Cloud drive and folder
* Cloned repository from distributed version control systems
```
$ sudo wac init
[sudo] password:
[wac] master password:
Code generated successfully into ~/.wac
```

I should be confident about exporting sensible and private information like passwords,  private keys, connection tokens,
web site credentials because they are stored in a highly secure encrypted format. So if the code is accidentally exposed
publicly, it should be impossible for someone to decrypt the sensible part without knowing my master password. But, to
allow this, I accept to remember one and only one super-strong master password that I will never ever disclose. The only
exception will be the master password of my password manager. I should never be confident enough to store it, even with
the highest existing encryption format. So because I see no good reason to store a master password of a password manager
on a computer's hard drive, then I will never have to export it (really don't do this).

Each time I change the computer state, I want to generate the code difference describing the change and I can store this
code in a version control system. So when I want, thanks to my version control system, I can restore a previous code
version and reapply it to restore a minor computer state change, automatically and reliably in a few minutes (non-related
to OS kind and version)
```
$ wac snapshot

# change manually something on my configuration...
$ apt install -y git gitk
$ git config --global user.email johndoe@example.com

$ wac diff -1
apt.pkg "git", "gitk"
git.config.global "user.email", "johndoe@example.com"
```

It should be easy for a friend of mine to share with me a snippet of code to install a list of software solutions and
configurations, regardless of the installation method (OS packages, dependency repositories, direct binary download,
built from source code, ...)
```
$ wac apply
```

If I want to play with a new OS kind or OS version, or more tragically if my computer or its hard drive crashes or
disappears into the cosmic void. I want to rebuild it from scratch, using a new computer or a new hard drive in less
than one hour.

I assume that:
* I have a fast internet connection, so I can download all artifacts in less than 30 minutes.
* I assume that I have a live installation USB key of my OS allowing command lines and internet access, or that my OS is already installed or restored in the initial state of the desired version on the computer.

```
$ curl -s "https://get.wac.io" | bash
$ wac install john-gamer-pc --from https://github.com/john/wac --to /dev/sdb
```

## About

For now, *Workstation As Code* is just a single individual initiative making voluntary open source contributions.

Contact [{{ site.email }}](mailto:{{ site.email }})
