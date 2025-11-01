CURR_MKFILE_DIR := $(patsubst %/, %, $(dir $(realpath $(lastword $(MAKEFILE_LIST)))))

include ${CURR_MKFILE_DIR}/default.env

build:
	docker build \
		-f Containerfile \
		--pull \
		--tag ghcr.io/lqhuang/shiho/s6-overlay:${S6_OVERLAY_VERSION} \
		--build-arg S6_OVERLAY_VERSION=${S6_OVERLAY_VERSION} \
		.
		#--tag docker.io/lqhuang/shiho/s6-overlay:${S6_OVERLAY_VERSION} \
		#--platform linux/amd64,linux/arm64,linux/riscv64 \

publish:
	# docker push docker.io/lqhuang/shiho/s6-overlay:${S6_OVERLAY_VERSION}
	docker push ghcr.io/lqhuang/shiho/s6-overlay:${S6_OVERLAY_VERSION}
