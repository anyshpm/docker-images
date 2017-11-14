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
