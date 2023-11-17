FROM alpine

#RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.ustc.edu.cn/g' /etc/apk/repositories
RUN apk add --no-cache ca-certificates tzdata python3 py3-pip curl wget bash tor gzip && \
    rm -rf /tmp/* && rm -rf /var/cache/apk/*
RUN pip3 install pyyaml
RUN wget -O /tmp/in_program.gz https://github.com/zhongfly/Clash-premium-backup/releases/download/2023-09-05-gdcc8d87/clash-linux-amd64-n2023-09-05-gdcc8d87.gz && gzip -d /tmp/in_program.gz && mv /tmp/in_program /usr/bin/in_program && chmod +x /usr/bin/in_program
VOLUME /data
COPY entrypoint.sh /entrypoint.sh
COPY init.py /init.py
RUN chmod +x /entrypoint.sh

ENTRYPOINT ["/entrypoint.sh"]
