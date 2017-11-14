## Something in docker
[![build status badge](https://travis-ci.org/anyshpm/docker-images.svg)](https://travis-ci.org/anyshpm/docker-images)

### Author
Anyshpm Chen (anyshpm@anyshpm.com)

### Usage

#### Trac

Supported tags:`1.2.2`, `latest`.

Example:

```
$ docker run -d --name trac -p 8000:80 -v/path/to/trac:/var/www/trac:rw anyshpm/trac:latest
```

#### Socks5

Supported tags:`3.8.9`, `latest`.

Example:

```
$ docker run -d --name socks5 -p 1080:1080 anyshpm/socks5:latest
```
