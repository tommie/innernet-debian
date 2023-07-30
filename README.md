# Unofficial Innernet APT Repository

[![Update Repository](https://github.com/tommie/innernet-debian/actions/workflows/main.yml/badge.svg?event=schedule)](https://github.com/tommie/innernet-debian/actions/workflows/main.yml)

This is a Debian/Ubuntu APT repository containing `.deb` files from https://github.com/tonarino/innernet/releases.
The updates are fully reproducible through GitHub Actions.

For more information, see https://github.com/tonarino/innernet.

## Installation

### Adding the Repository

```sh
codename=$(lsb_release --codename --short)
curl -sS https://tommie.github.io/innernet-debian/repository.asc | sudo tee /etc/apt/keyrings/github-tommie-innernet.asc >/dev/null
cat >/etc/apt/sources.list.d/innernet.list <<EOF
deb [signed-by=/etc/apt/keyrings/github-tommie-innernet.asc] https://tommie.github.io/innernet-debian/debian $codename contrib
EOF
apt update
```

### Installing the Server

This is installed on the coordination server machine.
It needs to be accessible from all peers.

```shell
$ sudo apt install innernet-server
```

### Installing the Peer Client

This is installed on all peers.

```shell
$ sudo apt install innernet
```

## Compatibility

We build for

* Ubuntu 20.04 (**focal**)
* Ubuntu 22.04 (**jammy**)

on

* **amd64**, x86_64
* **armhf**, armv7 (cross-build)
* **arm64**, aarch64 (cross-build)

Additionally:

* Debian 11 (**bullseye**) is served by `focal`.
  There is a symlink in place to allow `bullseye`, which will cause APT to warn that the codenames missmatch.
  In the end, either name works.

The authoritative source of supported distributions and architectures is [`conf/distributions`](https://github.com/tommie/innernet-debian/blob/main/debian/conf/distributions).

## License

The repository maintenance code itself is under the MIT License.
See also [LICENSE in tonarino/innernet](https://github.com/tonarino/innernet/blob/main/LICENSE).
