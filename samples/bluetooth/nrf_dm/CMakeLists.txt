#
# Copyright (c) 2021 Nordic Semiconductor
#
# SPDX-License-Identifier: LicenseRef-Nordic-5-Clause
#
cmake_minimum_required(VERSION 3.20)

set(ZEPHYR_EXTRA_MODULES
  $ENV{ZEPHYR_BASE}/../nrf
  $ENV{ZEPHYR_BASE}/../modules/lib/hostap
  $ENV{ZEPHYR_BASE}/../bootloader/mcuboot
  $ENV{ZEPHYR_BASE}/../modules/crypto/mbedtls
  $ENV{ZEPHYR_BASE}/../modules/tee/tf-m/trusted-firmware-m
  $ENV{ZEPHYR_BASE}/../modules/lib/cjson
  $ENV{ZEPHYR_BASE}/../modules/lib/azure-sdk-for-c
  $ENV{ZEPHYR_BASE}/../modules/lib/memfault-firmware-sdk
  $ENV{ZEPHYR_BASE}/../modules/hal/cirrus-logic
  $ENV{ZEPHYR_BASE}/../modules/lib/openthread
  $ENV{ZEPHYR_BASE}/../modules/lib/canopennode
  $ENV{ZEPHYR_BASE}/../modules/lib/chre
  $ENV{ZEPHYR_BASE}/../modules/fs/fatfs
  $ENV{ZEPHYR_BASE}/../modules/hal/nordic
  $ENV{ZEPHYR_BASE}/../modules/lib/liblc3
  $ENV{ZEPHYR_BASE}/../modules/fs/littlefs
  $ENV{ZEPHYR_BASE}/../modules/lib/loramac-node
  $ENV{ZEPHYR_BASE}/../modules/lib/gui/lvgl
  $ENV{ZEPHYR_BASE}/../modules/lib/lz4
  $ENV{ZEPHYR_BASE}/../modules/lib/nanopb
  $ENV{ZEPHYR_BASE}/../modules/lib/picolibc
  $ENV{ZEPHYR_BASE}/../modules/debug/TraceRecorder
  $ENV{ZEPHYR_BASE}/../modules/lib/uoscore-uedhoc
  $ENV{ZEPHYR_BASE}/../modules/lib/zcbor
  $ENV{ZEPHYR_BASE}/../modules/lib/zscilib
  $ENV{ZEPHYR_BASE}/../nrfxlib
  $ENV{ZEPHYR_BASE}/../modules/lib/matter

  $ENV{ZEPHYR_BASE}/../modules/hal/cmsis
  $ENV{ZEPHYR_BASE}/../modules/crypto/tinycrypt
  )

find_package(Zephyr REQUIRED HINTS $ENV{ZEPHYR_BASE})
project(nrf_dm)

# NORDIC SDK APP START
target_sources(app PRIVATE
  src/main.c
  src/pwm_led.c
  src/peer.c
  src/service.c
  )
# NORDIC SDK APP END

zephyr_library_include_directories(${CMAKE_CURRENT_SOURCE_DIR})
