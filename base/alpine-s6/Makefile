CURR_MKFILE_DIR := $(patsubst %/, %, $(dir $(realpath $(lastword $(MAKEFILE_LIST)))))

include ${CURR_MKFILE_DIR}/default.env

build:
	docker buildx build \
		-f Containerfile \
		--tag ghcr.io/lqhuang/alpine-s6:${ALPINE_DIST_TAG} \
		--tag docker.io/lqhuang/alpine-s6:${ALPINE_DIST_TAG} \
		--build-arg ALPINE_DIST_TAG=${ALPINE_DIST_TAG} \
		--build-arg S6_OVERLAY_VERSION=${S6_OVERLAY_VERSION} \
		.
		#--platform linux/amd64,linux/arm64,linux/riscv64 \

publish:
	docker push docker.io/lqhuang/alpine-s6:${ALPINE_DIST_TAG}
	docker push ghcr.io/lqhuang/alpine-s6:${ALPINE_DIST_TAG}
