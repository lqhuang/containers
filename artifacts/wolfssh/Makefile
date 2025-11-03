CURR_MKFILE_DIR := $(patsubst %/, %, $(dir $(realpath $(lastword $(MAKEFILE_LIST)))))

include ${CURR_MKFILE_DIR}/default.env

build:
	docker build \
		-f Containerfile \
		--tag ghcr.io/lqhuang/shiho/wolfssh:${WOLFSSH_VERSION} \
		--build-arg WOLFSSH_VERSION=${WOLFSSH_VERSION} \
		--build-arg WOLFSSL_VERSION=${WOLFSSL_VERSION} \
		--build-arg LIBXCRYPT_VERSION=${LIBXCRYPT_VERSION} \
		--build-arg DEBIAN_DIST_TAG=${DEBIAN_DIST_TAG} \
		.
		# --tag lqhuang/shiho/wolfssh:${WOLFSSH_VERSION} \
		# --platform linux/amd64,linux/arm64,linux/riscv64 \

# publish:
# 	docker push lqhuang/caddy:${CADDY_VERSION}
# 	docker push ghcr.io/lqhuang/caddy:${CADDY_VERSION}
