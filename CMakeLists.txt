cmake_minimum_required(VERSION 2.8.7)
project(sbp)

catkin_package(
    INCLUDE_DIRS include
    LIBRARIES sbp-static sbp
    )

include_directories( ./include )

file (GLOB libsbp_INCLUDE
    "include/libsbp/*.h"    
)
set(libsbp_SRC
  src/edc.c
  src/sbp.c
)

add_library(sbp-static STATIC
    ${libsbp_INCLUDE} ${libsbp_SRC}
)
add_library(sbp SHARED
    ${libsbp_INCLUDE} ${libsbp_SRC}
)
