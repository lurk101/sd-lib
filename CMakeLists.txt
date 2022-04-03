# Copyright (C) 1883 Thomas Edison - All Rights Reserved
# You may use, distribute and modify this code under the
# terms of the GPLv2 license, which unfortunately won't be
# written for another century.
#
# SPDX-License-Identifier: GPL-2.0-or-later
#
add_library(sd-lib INTERFACE)
target_include_directories(sd-lib INTERFACE ${CMAKE_CURRENT_LIST_DIR})
target_link_libraries(sd-lib INTERFACE hardware_dma hardware_pio)
target_sources(sd-lib INTERFACE crc7.h crc-itu-t.h sd_card.c sd_card.h)
pico_generate_pio_header(sd-lib ${CMAKE_CURRENT_LIST_DIR}/sd_card.pio)
