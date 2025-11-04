CURR_MKFILE_DIR := $(patsubst %/, %, $(dir $(realpath $(lastword $(MAKEFILE_LIST)))))

include ${CURR_MKFILE_DIR}/default.env

build:
	docker build \
		-f Containerfile \
		--pull \
		--tag ghcr.io/lqhuang/shiho/code-server:${CODE_SERVER_VERSION} \
		--build-arg CODE_SERVER_VERSION=${CODE_SERVER_VERSION} \
		.
		# --tag lqhuang/shiho/code-server:${CODE_SERVER_VERSION} \
		# --platform linux/amd64,linux/arm64,linux/riscv64 \

# publish:
# 	docker push lqhuang/caddy:${CADDY_VERSION}
# 	docker push ghcr.io/lqhuang/caddy:${CADDY_VERSION}
