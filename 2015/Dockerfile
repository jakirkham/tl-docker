FROM debian:jessie
MAINTAINER Henri Menke <texlive@henrimenke.de>
ENV DEBIAN_FRONTEND noninteractive
COPY texlive.profile /
RUN apt-get update \
  && apt-get install --no-install-recommends -y \
    wget perl fontconfig libwww-perl \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/* \
  && wget ftp://tug.org/historic/systems/texlive/2015/install-tl-unx.tar.gz \
  && tar xzvf install-tl-unx.tar.gz \
  && ./install-tl-*/install-tl -profile texlive.profile \
  -repository ftp://tug.org/historic/systems/texlive/2015/tlnet-final \
  && rm -rf install-tl-*
