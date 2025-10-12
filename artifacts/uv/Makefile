CURR_MKFILE_DIR := $(patsubst %/, %, $(dir $(realpath $(lastword $(MAKEFILE_LIST)))))

include ${CURR_MKFILE_DIR}/default.env

build:
	docker build \
		-f Containerfile \
		--tag ghcr.io/lqhuang/artifact-uv:${UV_VERSION} \
		--tag lqhuang/artifact-uv:${UV_VERSION} \
		--build-arg UV_VERSION=${UV_VERSION} \
		--build-arg MIYANO_VERSION=${MIYANO_VERSION} \
		.
		# --platform linux/amd64,linux/arm64,linux/riscv64 \

# publish:
# 	docker push lqhuang/caddy:${CADDY_VERSION}
# 	docker push ghcr.io/lqhuang/caddy:${CADDY_VERSION}
