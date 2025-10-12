CURR_MKFILE_DIR := $(patsubst %/, %, $(dir $(realpath $(lastword $(MAKEFILE_LIST)))))

include ${CURR_MKFILE_DIR}/default.env

build:
	@echo Given `S6_OVERLAY_VERSION` is ${S6_OVERLAY_VERSION}
	docker build \
		-f Containerfile \
		--pull \
		--tag ghcr.io/lqhuang/s6-dist:${S6_OVERLAY_VERSION} \
		--tag lqhuang/s6-dist:${S6_OVERLAY_VERSION} \
		--build-arg S6_OVERLAY_VERSION=${S6_OVERLAY_VERSION} \
		.
		--platform linux/amd64,linux/arm64,linux/riscv64 \

# publish:
# 	docker push lqhuang/caddy:${CADDY_VERSION}
# 	docker push ghcr.io/lqhuang/caddy:${CADDY_VERSION}
