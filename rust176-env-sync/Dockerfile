FROM registry.access.redhat.com/ubi8

RUN dnf install \
--assumeyes \
--disablerepo=* \
--enablerepo=rhel-8-for-x86_64-baseos-rpms \
--enablerepo=rhel-8-for-x86_64-appstream-rpms \
wget \
gcc \
openssl \
openssl-devel

RUN cd /tmp && \
wget --content-disposition --timestamping --continue https://static.rust-lang.org/dist/rust-1.76.0-x86_64-unknown-linux-gnu.tar.gz && \
mkdir -p /tmp/rust && \
tar --strip-components=1 -xzf rust-1.76.0-x86_64-unknown-linux-gnu.tar.gz -C /tmp/rust && \
/tmp/rust/install.sh && \
rm -rf /tmp/rust*  

COPY root/etc/pki/tls/certs/* /etc/pki/tls/certs/

RUN chmod +x /usr/local/bin/*

COPY root/usr/local/bin/* /usr/local/bin/

RUN chmod +x /usr/local/bin/*

CMD ["rust176-env-sync.bash"]
