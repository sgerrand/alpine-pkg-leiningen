# alpine-pkg-leiningen

[![CircleCI](https://img.shields.io/circleci/project/sgerrand/alpine-pkg-leiningen/master.svg)](https://circleci.com/gh/sgerrand/alpine-pkg-leiningen)

This is [Leiningen][leiningen] as an Alpine Linux package.

## Releases

See the [releases page][releases] for the latest download links.

## Installing

The current installation method for these packages is to pull them in using
`wget` or `curl` and install the local file with `apk`:

    apk --no-cache add ca-certificates
    wget -q -O /etc/apk/keys/sgerrand.rsa.pub https://raw.githubusercontent.com/sgerrand/alpine-pkg-leiningen/master/sgerrand.rsa.pub
    wget https://github.com/sgerrand/alpine-pkg-leiningen/releases/download/2.7.1-r0/leiningen-2.7.1-r0.apk
    apk add leiningen-2.7.1-r0.apk

[leiningen]: https://leiningen.org
[releases]: https://github.com/sgerrand/alpine-pkg-leiningen/releases/
