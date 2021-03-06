# Nim Compiler

[![Join the Chat at irc.freenode.net#nim](https://img.shields.io/badge/IRC-join_chat_in_%23nim-blue.svg)](https://webchat.freenode.net/?channels=nim)
[![Get help](https://img.shields.io/badge/Forum-get%20help-4eb899.svg)](http://forum.nim-lang.org)
[![Stackoverflow](https://img.shields.io/badge/stackoverflow-use_%23nim_tag-yellow.svg)](http://stackoverflow.com/questions/tagged/nim?sort=newest&pageSize=15)
[![Follow @nim_lang!](https://img.shields.io/twitter/follow/nim_lang.svg?style=social)](https://twitter.com/nim_lang)

[![Travis](https://img.shields.io/travis/nim-lang/Nim.svg)](https://travis-ci.org/nim-lang/Nim)

[![Contribute to Nim via Gratipay!](https://img.shields.io/gratipay/team/nim.svg)](https://gratipay.com/nim/)
[![Bountysource](https://img.shields.io/bountysource/team/nim/activity.svg)](https://www.bountysource.com/teams/nim)


This repo contains the Nim compiler, Nim's stdlib, tools and
documentation.

## Compiling
Compiling the Nim compiler is quite straightforward. Because
the Nim compiler itself is written in the Nim programming language
the C source of an older version of the compiler are needed to bootstrap the
latest version. The C sources are available in a separate
repo [here](http://github.com/nim-lang/csources).

The compiler currently supports the following platform and architecture
combinations:

  * Windows (Windows XP or greater) - x86 and x86_64
  * Linux (most, if not all, distributions) - x86, x86_64, ppc64 and armv6l
  * Mac OS X 10.04 or higher - x86, x86_64 and ppc64

In reality a lot more are supported, however they are not tested regularly.

To build from source you will need:

  * gcc 3.x or later recommended. Other alternatives which may work
    are: clang, Visual C++, Intel's C++ compiler
  * git or wget

If you are on a fairly modern *nix system, the following steps should work:

```
$ git clone https://github.com/nim-lang/Nim.git
$ cd Nim
$ git clone --depth 1 https://github.com/nim-lang/csources
$ cd csources && sh build.sh
$ cd ..
$ bin/nim c koch
$ ./koch boot -d:release
```

``koch install [dir]`` may then be used to install Nim, but lots of things
don't work then so don't do that. Add it to your PATH instead. More ``koch``
related options are documented in [doc/koch.txt](doc/koch.txt).

The above steps can be performed on Windows in a similar fashion, the
``build.bat`` and ``build64.bat`` (for x86_64 systems) are provided to be used
instead of ``build.sh``.


## Nimble
[Nimble](https://github.com/nim-lang/nimble) is Nim's package manager. For the
source based installations where you added Nim's ``bin`` directory to your PATH
the easiest way of installing Nimble is via:

```
$ nim e install_nimble.nims
```

## Getting help
A [forum](http://forum.nim-lang.org/) is available if you have any
questions, and you can also get help in the IRC channel on
[Freenode](irc://irc.freenode.net/nim) in #nim. If you ask questions on
[StackOverflow use the nim
tag](http://stackoverflow.com/questions/tagged/nim).

## License
The compiler and the standard library are licensed under the MIT license,
except for some modules where the documentation suggests otherwise. This means
that you can use any license for your own programs developed with Nim,
allowing you to create commercial applications.

Read copying.txt for more details.

Copyright (c) 2006-2016 Andreas Rumpf.
All rights reserved.

# Build Status
[**Build Waterfall**][waterfall]

|        | Linux | Windows | Mac |
| ------ | ----- | ------- | --- |
| x86    | [![linux-x86][linux-x86-img]][linux-x86] | [![windows-x86][windows-x86-img]][windows-x86] |
| x86_64 | [![linux-x86_64][linux-x86_64-img]][linux-x86_64] | [![windows-x86_64][windows-x86_64-img]][windows-x86_64] | [![mac-x86_64][mac-x86_64-img]][mac-x86_64] |
| arm    | [![linux-armv5][linux-arm5-img]][linux-arm5]<br/> [![linux-armv6][linux-arm6-img]][linux-arm6]<br/> [![linux-armv7][linux-arm7-img]][linux-arm7]

[linux-x86]:          http://buildbot.nim-lang.org/builders/linux-x32-builder
[linux-x86-img]:      http://buildbot.nim-lang.org/buildstatusimage?builder=linux-x32-builder
[linux-x86_64]:       http://buildbot.nim-lang.org/builders/linux-x64-builder
[linux-x86_64-img]:   http://buildbot.nim-lang.org/buildstatusimage?builder=linux-x64-builder
[linux-arm5]:         http://buildbot.nim-lang.org/builders/linux-arm5-builder
[linux-arm5-img]:     http://buildbot.nim-lang.org/buildstatusimage?builder=linux-arm5-builder
[linux-arm6]:         http://buildbot.nim-lang.org/builders/linux-arm6-builder
[linux-arm6-img]:     http://buildbot.nim-lang.org/buildstatusimage?builder=linux-arm6-builder
[linux-arm7]:         http://buildbot.nim-lang.org/builders/linux-arm7-builder
[linux-arm7-img]:     http://buildbot.nim-lang.org/buildstatusimage?builder=linux-arm7-builder

[windows-x86]:        http://buildbot.nim-lang.org/builders/windows-x32-builder
[windows-x86-img]:    http://buildbot.nim-lang.org/buildstatusimage?builder=windows-x32-builder
[windows-x86_64]:     http://buildbot.nim-lang.org/builders/windows-x64-builder
[windows-x86_64-img]: http://buildbot.nim-lang.org/buildstatusimage?builder=windows-x64-builder

[mac-x86_64]:         http://buildbot.nim-lang.org/builders/mac-x64-builder
[mac-x86_64-img]:     http://buildbot.nim-lang.org/buildstatusimage?builder=mac-x64-builder

[waterfall]: http://buildbot.nim-lang.org/waterfall
