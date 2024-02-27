# build
podman build -t ovsx-env-sync .

# shell
podman run --rm -it ovsx-env-sync /bin/bash

# run
podman run \
--name ovsx-env-sync \
--volume /export/ovsx:/export \
--volume ./root/projects:/projects \
--rm \
localhost/ovsx-env-sync
