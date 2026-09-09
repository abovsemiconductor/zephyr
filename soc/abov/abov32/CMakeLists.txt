# Copyright (c) 2026 ABOV Semiconductor Co., Ltd.
# SPDX-License-Identifier: Apache-2.0

file(GLOB product_line_match ${CMAKE_CURRENT_SOURCE_DIR}/*/${SOC_SERIES})
if(NOT product_line_match)
  message(FATAL_ERROR "No ABOV32 product-line directory provides SoC series '${SOC_SERIES}'")
endif()
cmake_path(GET product_line_match PARENT_PATH product_line_dir)
cmake_path(GET product_line_dir FILENAME product_line)

add_subdirectory(${product_line})
add_subdirectory(common)
