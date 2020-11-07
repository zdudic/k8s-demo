FROM docker.io/oraclelinux:7

RUN mkdir /root/.ssh && chmod 700 /root/.ssh
COPY root-id_rsa /root/.ssh/id_rsa
RUN chown root:root /root/.ssh/id_rsa && chmod 400 /root/.ssh/id_rsa
COPY bugzilla-stage-backup.sh /bugzilla-stage-backup.sh

# replace YOUR-FQDN  with your real hostname
CMD /bin/scp -i /root/.ssh/id_rsa -o "StrictHostKeyChecking no" /bugzilla-stage-backup.sh YOUR-FQDN:/tmp && /bin/ssh -i /root/.ssh/id_rsa -o "StrictHostKeyChecking no" YOUR-FQDN /tmp/bugzilla-stage-backup.sh

