# build
podman build -t maven36-env-sync .

# shell
podman run --rm -it maven36-env-sync /bin/bash

# run
podman run \
--name maven36-env-sync \
--volume /export/maven/maven36:/export \
--volume ./root/projects:/projects \
--rm \
localhost/maven36-env-sync

# run - cache
podman run \
--name maven36-env-sync \
--volume /export/maven/maven36:/export \
--volume ./root/projects:/projects \
--volume ./root/.m2/settings.xml:/root/.m2/settings.xml \
--rm \
localhost/maven36-env-sync
