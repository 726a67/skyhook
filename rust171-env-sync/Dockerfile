FROM registry.access.redhat.com/ubi8

RUN dnf install \
--assumeyes \
--disablerepo=* \
--enablerepo=rhel-8-for-x86_64-baseos-rpms \
--enablerepo=rhel-8-for-x86_64-appstream-rpms \
rust \
cargo

#COPY root/etc/pki/ca-trust/source/anchors/* /etc/pki/ca-trust/source/anchors/

#RUN update-ca-trust

COPY root/etc/pki/tls/certs/* /etc/pki/tls/certs/

COPY root/usr/local/bin/* /usr/local/bin/

RUN chmod +x /usr/local/bin/*

CMD ["rust-env-sync.bash"]
