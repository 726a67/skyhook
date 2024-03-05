# build
podman build -t python39-env-sync .

# shell
podman run --rm -it python39-env-sync /bin/bash

# run - caching proxy
podman run \
--name python39-env-sync \
--volume ./root/projects:/projects \
--rm \
localhost/python39-env-sync

# run - caching proxy + local cache
podman run \
--name python39-env-sync \
--volume /var/tmp/python/python39:/export \
--volume ./root/projects:/projects \
--volume ./root/.pip/pip.conf:/root/.pip/pip.conf \
--rm \
localhost/python39-env-sync

# run - no caching proxy + local cache
podman run \
--name python39-env-sync \
--volume /var/tmp/python/python39:/export \
--volume ./root/projects:/projects \
--rm \
localhost/python39-env-sync
