# debian-asdf

[![GitHub](https://img.shields.io/github/v/tag/caspiandb/docker-debian-asdf?label=GitHub)](https://github.com/caspiandb/docker-debian-asdf)
[![CI](https://github.com/caspiandb/docker-debian-asdf/actions/workflows/ci.yaml/badge.svg)](https://github.com/caspiandb/docker-debian-asdf/actions/workflows/ci.yaml)
[![Trunk Check](https://github.com/caspiandb/docker-debian-asdf/actions/workflows/trunk.yaml/badge.svg)](https://github.com/caspiandb/docker-debian-asdf/actions/workflows/trunk.yaml)
[![Docker Image Version](https://img.shields.io/docker/v/caspiandb/debian-asdf/latest?label=docker&logo=docker)](https://hub.docker.com/r/caspiandb/debian-asdf)

Container image with [asdf](https://asdf-vm.com/) installer based on Debian 11 "bullseye".

Additional Debian packages:

- [ca-certificates](https://packages.debian.org/bullseye/ca-certificates)
- [curl](https://packages.debian.org/bullseye/curl)
- [git](https://packages.debian.org/bullseye/git)
- [procps](https://packages.debian.org/bullseye/procps)
- [unzip](https://packages.debian.org/bullseye/unzip)
- [xz-utils](https://packages.debian.org/bullseye/xz-utils)

## Tags

- `asdf-X.Y.Z-bullseye-YYYYmmdd`, `asdf-X.Y.Z`, `latest`

## Usage

CLI:

```shell
docker pull caspiandb/debian-asdf
docker run caspiandb/debian-asdf bash -c "asdf plugin add nodejs && asdf install nodejs latest && asdf global nodejs latest && node -v"
```

Dockerfile:

```Dockerfile
FROM caspiandb/debian-asdf:latest
COPY .tool-versions /root/
RUN cat .tool-versions | while read plugin version; do asdf plugin add $plugin; done
RUN asdf install
RUN asdf list
```

## License

[License information](https://github.com/asdf-vm/asdf/blob/master/LICENSE) for
[asdf](https://asdf-vm.com/) project.

[License
information](https://github.com/caspiandb/docker-debian-asdf/blob/main/LICENSE) for
container image project.
