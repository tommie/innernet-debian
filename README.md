# Unofficial Innernet APT Repository

This is a Debian/Ubuntu APT repository containing `.deb` files from
https://github.com/tonarino/innernet/releases. The updates are
automatic and running on a biweekly schedule.

For more information, see https://github.com/tonarino/innernet.

## Installation

### Adding the Repository

```shell
$ curl -sS https://tommie.github.io/innernet-debian/repository.key | apt-key add -
OK
$ cat >/etc/apt/sources.list.d/innernet.list <<EOF
deb https://tommie.github.io/innernet-debian/debian unstable contrib
EOF
$ apt update
...
Get:5 https://tommie.github.io/innernet-debian/debian unstable InRelease [1.729 B]
...
```

### Installing the Server

This is installed on the coordination server machine. It needs to be
accessible from all peers.

```shell
$ apt install innernet-server
```

### Installing the Peer Client

This is installed on all peers.

```shell
$ apt install innernet
```

## License

The repository maintenance code itself is under the MIT License. See
also [LICENSE in
tonarino/innernet](https://github.com/tonarino/innernet/blob/main/LICENSE).
