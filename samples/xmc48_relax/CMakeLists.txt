# Copyright (c) 2022, Stefano Cottafavi <stefano.cottafavi@gmail.com>
#
# SPDX-License-Identifier: Apache-2.0

# Add the driver directory as a zephyr module by hand
list(APPEND ZEPHYR_EXTRA_MODULES
#	${CMAKE_CURRENT_SOURCE_DIR}/../../drivers
)

set(
	BOARD_ROOT ${CMAKE_CURRENT_SOURCE_DIR}/../..
)

cmake_minimum_required(VERSION 3.20.0)

# required for apps
find_package(Zephyr REQUIRED HINTS $ENV{ZEPHYR_BASE})

project(xmc48-relax)

zephyr_include_directories(src)

target_sources(app PRIVATE
	src/main.c
)
