## Something in docker
[![build status badge](https://travis-ci.org/anyshpm/docker-images.svg)](https://travis-ci.org/anyshpm/docker-images)

### Author
Anyshpm Chen (anyshpm@anyshpm.com)

### Usage

#### trac
[![layers badge](https://images.microbadger.com/badges/image/anyshpm/trac.svg)](https://microbadger.com/images/anyshpm/trac)

Supported tags:`1.2.2`, `latest`.

Example:

```
$ docker run -d --name trac -p 8000:80 -v/path/to/trac:/var/www/trac:rw anyshpm/trac:latest
```

#### socks5
[![layers badge](https://images.microbadger.com/badges/image/anyshpm/socks5.svg)](https://microbadger.com/images/anyshpm/socks5)

Supported tags:`3.8.9`, `latest`.

Example:

```
$ docker run -d --name socks5 -p 1080:1080 anyshpm/socks5:latest
```

### ipsec-vpn
[![layers badge](https://images.microbadger.com/badges/image/anyshpm/ipsec-vpn.svg)](https://microbadger.com/images/anyshpm/ipsec-vpn)

Thanks @hwdsl2's entrypoint script: [run.sh](https://github.com/hwdsl2/docker-ipsec-vpn-server/blob/0f9fbbc0eddb77437cf970bf38525a0845229ade/run.sh)

Supported tags:`1.0`, `latest`.

Example:

```
docker run --name ipsec -d --privileged -v /lib/modules:/lib/modules:ro -p 4500:4500/udp -p 500:500/udp --restart=always --env-file ./vpn.env anyshpm/ipsec-vpn:1.0
```
