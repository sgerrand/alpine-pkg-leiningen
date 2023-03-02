# alpine-pkg-leiningen

[![CircleCI](https://circleci.com/gh/sgerrand/alpine-pkg-leiningen.svg?style=svg)](https://circleci.com/gh/sgerrand/alpine-pkg-leiningen)

This is [Leiningen][leiningen] as an Alpine Linux package.

## Releases

See the [releases page][releases] for the latest download links.

## Installing

The current installation method for this package is to install it with `apk`:

    wget -P /etc/apk/keys/ https://alpine-pkgs.sgerrand.com/sgerrand.rsa.pub
    wget https://github.com/sgerrand/alpine-pkg-leiningen/releases/download/2.9.8-r0/leiningen-2.9.8-r0.apk
    apk leiningen=2.9.8-r0.apk

[leiningen]: https://leiningen.org
[releases]: https://github.com/sgerrand/alpine-pkg-leiningen/releases/
