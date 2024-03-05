# build
podman build -t nodejs20-env-sync .

# shell
podman run --rm -it nodejs20-env-sync /bin/bash

# run - caching proxy
podman run \
--name nodejs20-env-sync \
--volume ./root/projects:/projects \
--volume ./root/.npmrc:/root/.npmrc \
--volume ./root/.nrc:/root/.nrc \
--rm \
localhost/nodejs20-env-sync

# run - caching proxy + local cache
podman run \
--name nodejs20-env-sync \
--volume /var/tmp/node/nodejs20:/export \
--volume ./root/projects:/projects \
--volume ./root/.npmrc:/root/.npmrc \
--volume ./root/.nrc:/root/.nrc \
--rm \
localhost/nodejs20-env-sync

# run - no caching proxy + local cache
podman run \
--name nodejs20-env-sync \
--volume /export/node/nodejs20:/export \
--volume ./root/projects:/projects \
--rm \
localhost/nodejs20-env-sync
