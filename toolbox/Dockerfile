FROM alpine:3.11

WORKDIR /root

RUN apk add bash curl net-tools ncdu tree \
    && echo "export PS1='[\u@\h \W]\$ '" > /root/.bashrc \
    && echo "alias ll='ls -lh --color'" >> /root/.bashrc \
    && echo "alias la='ls -lah --color'" >> /root/.bashrc \
    && echo "alias dudu='du -sh *'" >> /root/.bashrc \
    && echo "alias vim='vi'" >> /root/.bashrc

CMD ["cat","/etc/os-release"]
