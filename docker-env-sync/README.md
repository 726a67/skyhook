# build
podman build -t docker-env-sync .

# run - caching proxy
podman run \
--name docker-env-sync \
--privileged \
--volume ./root/projects:/projects \
--volume ./root/.config/containers/registries.conf:/root/.config/containers/registries.conf \
--volume ./root/etc/containers/policy.json:/etc/containers/policy.json \
--rm \
localhost/docker-env-sync

# run - caching proxy + local cache
podman run \
--name docker-env-sync \
--privileged \
--volume /var/tmp/containers:/var/lib/containers:rw \
--volume /export/docker:/export \
--volume ./root/projects:/projects \
--volume ./root/.config/containers/registries.conf:/root/.config/containers/registries.conf \
--volume ./root/etc/containers/policy.json:/etc/containers/policy.json \
--rm \
localhost/docker-env-sync

# run - no caching proxy + local cache
podman run \
--name docker-env-sync \
--privileged \
--volume /var/tmp/containers:/var/lib/containers:rw \
--volume /export/docker:/export \
--volume ./root/projects:/projects \
--rm \
localhost/docker-env-sync
