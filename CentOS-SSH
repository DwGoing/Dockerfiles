FROM centos
RUN echo -e '#!/bin/bash' > start.sh \
&& echo -e '\n/usr/sbin/sshd -D' >> start.sh \
&& chmod 755 start.sh
RUN curl --output /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-8.repo \
&& yum makecache \
&& yum install -y openssh-server passwd \
&& ssh-keygen -t rsa -f /etc/ssh/ssh_host_rsa_key -N '' \
&& ssh-keygen -t ecdsa -f /etc/ssh/ssh_host_ecdsa_key -N '' \
&& ssh-keygen -t ed25519 -f /etc/ssh/ssh_host_ed25519_key -N '' \
&& sed -i -r 's/^(.*pam_nologin.so)/#\1/' /etc/pam.d/sshd
EXPOSE 22
ENTRYPOINT ["/start.sh"]
