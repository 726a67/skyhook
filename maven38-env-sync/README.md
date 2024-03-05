# build
podman build -t maven38-env-sync .

# shell
podman run --rm -it maven38-env-sync /bin/bash

# run - caching proxy
podman run \
--name maven38-env-sync \
--volume ./root/projects:/projects \
--volume ./root/.m2/settings.xml:/root/.m2/settings.xml \
--rm \
localhost/maven38-env-sync

# run - caching proxy + local cache
podman run \
--name maven38-env-sync \
--volume /var/tmp/maven/maven38:/export \
--volume ./root/projects:/projects \
--volume ./root/.m2/settings.xml:/root/.m2/settings.xml \
--rm \
localhost/maven38-env-sync

# run - no caching proxy + local cache
podman run \
--name maven38-env-sync \
--volume /var/tmp/maven/maven38:/export \
--volume ./root/projects:/projects \
--rm \
localhost/maven38-env-sync
