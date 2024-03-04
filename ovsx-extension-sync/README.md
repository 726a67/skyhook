# build
podman build -t ovsx-extension-sync .

# shell
podman run --rm -it ovsx-extension-sync /bin/bash

# run
podman run \
--name ovsx-extension-sync \
--volume /export/ovsx:/export \
--volume ./root/projects:/projects \
--rm \
localhost/ovsx-extension-sync
