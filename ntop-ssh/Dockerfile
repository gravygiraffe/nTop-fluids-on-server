FROM us-docker.pkg.dev/ntopweb/ntop-automate/ntop-automate:5.54.2

USER root

RUN dnf install -y \
        openssh-server \
        passwd \
        tmux \
        nano \
        && ssh-keygen -A \
        && dnf clean all

RUN mkdir -p /run/sshd

COPY startup.sh /startup.sh
RUN chmod +x /startup.sh

ENTRYPOINT ["/startup.sh"]

# How to build and push:
# docker build -t gravygravy/ntop-ssh .
# docker push gravygravy/ntop-ssh
