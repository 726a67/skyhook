FROM registry.access.redhat.com/ubi8

RUN dnf install \
--assumeyes \
--disablerepo=* \
--enablerepo=rhel-8-for-x86_64-baseos-rpms \
--enablerepo=rhel-8-for-x86_64-appstream-rpms \
rust \
cargo

#RUN npm install --silent --global npm

#RUN npm install --silent --global --prefix /usr/local ovsx

COPY root/usr/local/bin/* /usr/local/bin/

RUN chmod +x /usr/local/bin/*

CMD ["rust-env-sync.bash"]
