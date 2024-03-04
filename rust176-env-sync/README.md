# build
podman build -t rust176-env-sync .

# shell
podman run --rm -it rust176-env-sync /bin/bash

# run
podman run \
--name rust176-env-sync \
--volume /export/rust:/export \
--volume ./root/projects:/projects \
--rm \
localhost/rust176-env-sync

# run (cache)
podman run \
--name rust176-env-sync \
--volume /export/rust:/export \
--volume ./root/projects:/projects \
--volume ./root/.cargo/config.toml:/root/.cargo/config.toml \
--rm \
localhost/rust176-env-sync
