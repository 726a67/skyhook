# build
podman build -t rhel8-repo-sync .

# shell
podman run --rm -it rhel8-repo-sync /bin/bash

# run
podman run \
--name rhel8-repo-sync \
--volume /export/rhel:/export \
--volume ./root/releases.txt:/releases.txt \
--volume ./root/requirements.txt:/requirements.txt \
--rm \
localhost/rhel8-repo-sync
