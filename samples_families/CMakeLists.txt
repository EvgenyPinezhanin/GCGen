set(target "${GCGEN_LIBRARY_FAMILIES}")

file(GLOB hdrs "${CMAKE_CURRENT_SOURCE_DIR}/*/*.h*")
file(GLOB srcs "${CMAKE_CURRENT_SOURCE_DIR}/*/*.cpp")

add_library(${target} STATIC ${srcs} ${hdrs})
target_link_libraries(${target} ${LIBRARY_DEPS} ${GCGEN_LIBRARY})

# REPORT
message(STATUS "")
message(STATUS "General configuration for lib_${target}")
message(STATUS "OK")
message(STATUS "")
