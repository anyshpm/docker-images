NS = anyshpm
NM = ipsec-vpn
NAME = $(NS)/$(NM)

default: build

build:
	docker build --rm \
		-t $(NAME) \
		--build-arg BUILD_DATE=`date -u +"%Y-%m-%dT%H:%M:%SZ"` \
		--build-arg VCS_REF=`git rev-parse --short HEAD` .

push:
	docker push $(NAME)

debug:
	docker run --rm -it $(NAME) /bin/bash

run:
	docker run --name $(NM) -d --privileged -v /lib/modules:/lib/modules:ro -p 4500:4500/udp -p 500:500/udp --restart=always --env-file ./vpn.env $(NAME)

clean:
	docker stop $(NM)
	docker rm $(NM)

release: build push
