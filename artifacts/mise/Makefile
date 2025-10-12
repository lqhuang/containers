CURR_MKFILE_DIR := $(patsubst %/, %, $(dir $(realpath $(lastword $(MAKEFILE_LIST)))))

include ${CURR_MKFILE_DIR}/default.env

build:
	docker build \
		-f Containerfile \
		--pull \
		--tag ghcr.io/lqhuang/artifact-mise:${MISE_VERSION} \
		--tag lqhuang/artifact-mise:${MISE_VERSION} \
		--build-arg MISE_VERSION=${MISE_VERSION} \
		.
		# --platform linux/amd64,linux/arm64,linux/riscv64 \

# publish:
# 	docker push lqhuang/caddy:${CADDY_VERSION}
# 	docker push ghcr.io/lqhuang/caddy:${CADDY_VERSION}
