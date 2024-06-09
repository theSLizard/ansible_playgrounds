FROM alpine:latest

RUN apk update && apk add openssh \
    && mkdir /root/.ssh \
    && chmod 700 /root/.ssh \
    && ssh-keygen -A \
    && echo "PermitRootLogin yes" >> /etc/ssh/sshd_config \
    && echo "PasswordAuthentication yes" >> /etc/ssh/sshd_config

EXPOSE 22

CMD ["/usr/sbin/sshd", "-D"]
