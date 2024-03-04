# build
podman build -t rust-env-sync .

# shell
podman run --rm -it rust-env-sync /bin/bash

# run
podman run \
--name rust-env-sync \
--volume /export/rust:/export \
--volume ./root/projects:/projects \
--rm \
localhost/rust-env-sync
