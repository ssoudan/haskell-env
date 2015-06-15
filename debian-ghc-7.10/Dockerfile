FROM armhfbuild/debian
MAINTAINER sebastien.soudan@gmail.com

ADD testing.list /etc/apt/sources.list.d/testing.list
ADD unstable.list /etc/apt/sources.list.d/unstable.list
ADD experimental.list /etc/apt/sources.list.d/experimental.list

ADD prefs /etc/apt/preferences.d/prefs

ADD qemu-arm-static /usr/bin/qemu-arm-static
RUN apt-get update ; apt-get install -y ghc=7.10.1-5 cabal-install

RUN apt-get install -y zlib1g-dev
RUN cabal update ; cabal install cabal cabal-install

RUN apt-get clean
RUN rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

