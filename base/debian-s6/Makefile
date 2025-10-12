CURR_MKFILE_DIR := $(patsubst %/, %, $(dir $(realpath $(lastword $(MAKEFILE_LIST)))))

include ${CURR_MKFILE_DIR}/default.env

build:
	@echo Given 'DEBIAN_DIST_TAG' is ${DEBIAN_DIST_TAG}
	@echo Given 'S6_OVERLAY_VERSION' is ${S6_OVERLAY_VERSION}
	docker buildx build \
		-f Containerfile \
		--tag ghcr.io/lqhuang/debian-s6:${DEBIAN_DIST_TAG} \
		--tag lqhuang/debian-s6:${DEBIAN_DIST_TAG} \
		--build-arg DEBIAN_DIST_TAG=${DEBIAN_DIST_TAG} \
		--build-arg S6_OVERLAY_VERSION=${S6_OVERLAY_VERSION} \
		--platform linux/amd64,linux/arm64,linux/riscv64 \
		.

# publish:
# 	docker push lqhuang/caddy:${CADDY_VERSION}
# 	docker push ghcr.io/lqhuang/caddy:${CADDY_VERSION}
