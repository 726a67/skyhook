# build
podman build -t nodejs14-package-sync .

# run
podman run \
--name nodejs14-package-sync-sync \
--volume /export/nodejs14:/export \
--volume ./root/projects:/projects \
--rm \
localhost/nodejs14-package-sync