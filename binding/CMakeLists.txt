# ------------------------------------------------------------------------------
#
# Copyright 2016 The Arken Platform Authors.
#
# All rights reserved.
# Use of this source code is governed by a CPOL
# license that can be found in the LICENSE file.
#
# ------------------------------------------------------------------------------

include_directories(.)
include_directories(${PROJECT_SOURCE_DIR}/include)
include_directories(${PROJECT_SOURCE_DIR}/deps/include)
set(LIBRARY_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/clib/arken/doc)
set(LIBRARY_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/clib/arken/doc)

add_library(
  Excel SHARED excel.cpp
)

find_package(Qt5Core)
find_package(Qt5Network)
find_package(Qt5Gui)
find_package(Qt5Widgets)

set_target_properties(Excel PROPERTIES PREFIX "")

target_link_libraries(Excel Qt5::Core Qt5::Network Qt5::Gui Qt5::Widgets arken lua excel)
