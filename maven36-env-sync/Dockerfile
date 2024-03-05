FROM registry.access.redhat.com/ubi8

RUN dnf module install \
--assumeyes \
--disablerepo=* \
--enablerepo=rhel-8-for-x86_64-baseos-rpms \
--enablerepo=rhel-8-for-x86_64-appstream-rpms \
maven:3.6/common

COPY root/etc/pki/tls/certs/* /etc/pki/tls/certs/

RUN keytool -trustcacerts -keystore /etc/pki/ca-trust/extracted/java/cacerts -storepass changeit -importcert -alias artifactory -file /etc/pki/tls/certs/artifactory.crt -noprompt

COPY root/usr/local/bin/* /usr/local/bin/

RUN chmod +x /usr/local/bin/*

RUN mkdir /export

CMD ["maven36-env-sync.bash"]
