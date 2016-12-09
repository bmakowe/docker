FROM ubuntu:latest
    
RUN apt-get install -qy curl && \
    echo "deb http://shell.ninthgate.se/packages/debian wheezy main" > /etc/apt/sources.list.d/plexmediaserver.list && \
    curl http://shell.ninthgate.se/packages/shell-ninthgate-se-keyring.key | apt-key add - && \
    apt-get -q update && \
    apt-get install -qy --force-yes plexmediaserver && \
    apt-get -y autoremove && \
    apt-get -y clean && \
    rm -rf /var/lib/apt/lists/* && \
    rm -rf /tmp/*

VOLUME ["/config","/data"]

ADD ./start.sh /start.sh

RUN chmod u+x  /start.sh

ADD ./supervisord.conf /etc/supervisor/conf.d/supervisord.conf

ENV RUN_AS_ROOT="true" \
    CHANGE_DIR_RIGHTS="false"


EXPOSE 32400
EXPOSE 1900
EXPOSE 3005
EXPOSE 5353
EXPOSE 8324
EXPOSE 32410
EXPOSE 32412
EXPOSE 32413
EXPOSE 32414
EXPOSE 32469

CMD ["/start.sh"]
