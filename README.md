# alpine-pkg-leiningen

[![CircleCI](https://circleci.com/gh/sgerrand/alpine-pkg-leiningen.svg?style=svg)](https://circleci.com/gh/sgerrand/alpine-pkg-leiningen)

This is [Leiningen][leiningen] as an Alpine Linux package.

## Releases

See the [releases page][releases] for the latest download links.

## Installing

The current installation method for this package is to install it with `apk`:

    wget -P /etc/apk/keys/ https://alpine-pkgs.sgerrand.com/sgerrand.rsa.pub
    apk add --no-cache --repository=https://apkproxy.herokuapp.com/sgerrand/alpine-pkg-leiningen leiningen=2.9.2-r0

[leiningen]: https://leiningen.org
[releases]: https://github.com/sgerrand/alpine-pkg-leiningen/releases/
