set(target "${GCGEN_LIBRARY}")

file(GLOB hdrs "${GCGEN_INCLUDE}/*.h*")
file(GLOB srcs "${GCGEN_SOURCE}/*.cpp")

add_library(${target} STATIC ${srcs} ${hdrs})
target_link_libraries(${target} ${LIBRARY_DEPS})

# REPORT
message( STATUS "")
message( STATUS "General configuration for lib_${target}")
message( STATUS "OK")
message( STATUS "")
