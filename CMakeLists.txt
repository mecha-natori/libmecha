cmake_minimum_required(VERSION 3.1)
enable_language(CXX)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

project(mecha)

set(PROJECT_ROOT ${CMAKE_SOURCE_DIR})
if(LIBMECHA_ONLY)
    set(PROJECT_ROOT ${CMAKE_SOURCE_DIR}/..)
endif()

include_directories(include)
include_directories(${PROJECT_ROOT}/Core/Inc)
include_directories(${PROJECT_ROOT}/Drivers/CMSIS/Device/ST/STM32F4xx/Include)
include_directories(${PROJECT_ROOT}/Drivers/CMSIS/Include)
include_directories(${PROJECT_ROOT}/Drivers/STM32F4xx_HAL_Driver/Inc)

file(GLOB SRCS src/*.cc src/**/*.cc)

add_library(mecha STATIC ${SRCS})

