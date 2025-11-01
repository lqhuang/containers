.ONESHELL:
SHELL := /usr/bin/bash

build:
	set -eu -o pipefail
	FINDED=$$(find -maxdepth 2 -mindepth 2 -type f -name 'Makefile' -printf '%p ')
	read -ra DIRS <<< "$${FINDED}"
	for submkfile in $${DIRS[@]}; do
	  echo "$${submkfile}"
	  make -C $$(dirname "$${submkfile}") build
	done
