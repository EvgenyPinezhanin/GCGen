cmake_minimum_required(VERSION 3.20)

set(PROJECT_NAME gcgen)
set(CMAKE_CXX_STANDARD 11)

project (${PROJECT_NAME})

set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY_RELEASE ${CMAKE_BINARY_DIR}/bin/release)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY_DEBUG ${CMAKE_BINARY_DIR}/bin/debug)

set(GCGEN_LIBRARY ${PROJECT_NAME})
set(GCGEN_LIBRARY_FAMILIES ${PROJECT_NAME}_families)
set(GCGEN_INCLUDE ${CMAKE_CURRENT_SOURCE_DIR}/include ${CMAKE_CURRENT_SOURCE_DIR}/samples_families/)
set(GCGEN_SOURCE ${CMAKE_CURRENT_SOURCE_DIR}/src)

set(GCGEN_LIB_NAME ${PROJECT_NAME} CACHE STRING "" FORCE)
set(GCGEN_LIB_FAM_NAME ${PROJECT_NAME}_families CACHE STRING "" FORCE)
set(GCGEN_INC_NAME ${GCGEN_INCLUDE} CACHE PATH "" FORCE)

include_directories(${GCGEN_INCLUDE})

# BUILD
add_subdirectory(samples)
add_subdirectory(samples_families)
add_subdirectory(src)

# REPORT
message( STATUS "")
message( STATUS "General configuration for ${PROJECT_NAME}")
message( STATUS "======================================")
message( STATUS "")
message( STATUS "   Configuration: ${CMAKE_BUILD_TYPE}")
message( STATUS "")
