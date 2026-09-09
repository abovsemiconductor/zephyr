# Copyright (c) 2026 ABOV Semiconductor Co., Ltd.
# SPDX-License-Identifier: Apache-2.0

zephyr_include_directories(${ZEPHYR_BASE}/drivers)
zephyr_sources(soc.c)

zephyr_include_directories(.)

set(SOC_LINKER_SCRIPT ${ZEPHYR_BASE}/include/zephyr/arch/arm/cortex_m/scripts/linker.ld CACHE INTERNAL "")

zephyr_include_directories(
  ${ZEPHYR_ABOV32_MODULE_DIR}/audk32/ProductConfig/A31xxxx/A31C15x/Config
)

zephyr_compile_definitions(EXTRN_SUBFAMILY_A31C15x)

if(CONFIG_SOC_A31C156)
  zephyr_compile_definitions(EXTRN_VARIANT_A31C156RLN)
endif()
