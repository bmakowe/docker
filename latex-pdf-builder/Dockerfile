FROM          debian
MAINTAINER    Björn Antonio Makowe

ENV           TZ="Europe/Berlin"

RUN           echo "Europe/Berlin" | tee /etc/timezone \
           && dpkg-reconfigure --frontend noninteractive tzdata \
           && apt-get update \
           && apt-get install -y git \
                                 texlive-full \
                                 biber \
           && apt-get --purge -y remove texlive-*-doc \
           && apt-get clean \
           && rm -rf /var/lib/apt/lists/* \
                     /tmp/* /var/tmp/* \
	             /usr/share/man/?? \
	             /usr/share/man/??_*

