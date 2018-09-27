# alpine-pkg-leiningen

[![CircleCI](https://circleci.com/gh/sgerrand/alpine-pkg-leiningen.svg?style=svg)](https://circleci.com/gh/sgerrand/alpine-pkg-leiningen)

This is [Leiningen][leiningen] as an Alpine Linux package.

## Releases

See the [releases page][releases] for the latest download links.

## Installing

The current installation method for these packages is to pull them in using
`wget` or `curl` and install the local file with `apk`:

    apk --no-cache add ca-certificates
    wget -P /etc/apk/keys/ https://alpine-pkgs.sgerrand.com/sgerrand.rsa.pub
    wget https://github.com/sgerrand/alpine-pkg-leiningen/releases/download/2.8.1-r0/leiningen-2.8.1-r0.apk
    apk add leiningen-2.8.1-r0.apk

[leiningen]: https://leiningen.org
[releases]: https://github.com/sgerrand/alpine-pkg-leiningen/releases/
