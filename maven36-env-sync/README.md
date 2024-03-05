# build
podman build -t maven36-env-sync .

# shell
podman run --rm -it maven36-env-sync /bin/bash

# run - caching proxy
podman run \
--name maven36-env-sync \
--volume ./root/projects:/projects \
--volume ./root/.m2/settings.xml:/root/.m2/settings.xml \
--rm \
localhost/maven36-env-sync

# run - caching proxy + local cache
podman run \
--name maven36-env-sync \
--volume /var/tmp/maven/maven36:/export \
--volume ./root/projects:/projects \
--volume ./root/.m2/settings.xml:/root/.m2/settings.xml \
--rm \
localhost/maven36-env-sync

# run - no caching proxy + local cache
podman run \
--name maven36-env-sync \
--volume /var/tmp/maven/maven36:/export \
--volume ./root/projects:/projects \
--rm \
localhost/maven36-env-sync
