FROM registry.access.redhat.com/ubi8

RUN dnf module install \
--assumeyes \
--disablerepo=* \
--enablerepo=rhel-8-for-x86_64-baseos-rpms \
--enablerepo=rhel-8-for-x86_64-appstream-rpms \
python39

RUN dnf install \
--assumeyes \
gcc \
krb5-devel \
python39-devel

COPY root/usr/local/bin/* /usr/local/bin/

RUN chmod +x /usr/local/bin/*

RUN mkdir /export

CMD ["python39-env-sync.bash"]
