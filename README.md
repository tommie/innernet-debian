# Unofficial Innernet APT Repository

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

See [`dists/`](https://github.com/tommie/innernet-debian/tree/main/debian/dists) for supported codenames.

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

## License

The repository maintenance code itself is under the MIT License.
See also [LICENSE in tonarino/innernet](https://github.com/tonarino/innernet/blob/main/LICENSE).
