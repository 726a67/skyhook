# build
podman build -t python311-env-sync .

# shell
podman run --rm -it python311-env-sync /bin/bash

# run - caching proxy
podman run \
--name python311-env-sync \
--volume ./root/projects:/projects \
--volume ./root/.pip/pip.conf:/root/.pip/pip.conf \
--rm \
localhost/python311-env-sync

# run - caching proxy + local cache
podman run \
--name python311-env-sync \
--volume /export/python/python311:/export \
--volume ./root/projects:/projects \
--volume ./root/.pip/pip.conf:/root/.pip/pip.conf \
--rm \
localhost/python311-env-sync

# run - no caching proxy + local cache
podman run \
--name python311-env-sync \
--volume /export/python/python311:/export \
--volume ./root/projects:/projects \
--rm \
localhost/python311-env-sync
