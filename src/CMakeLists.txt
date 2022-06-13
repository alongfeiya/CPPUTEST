# set CPPUTEST as project name
set(BINARY ${CMAKE_PROJECT_NAME})

# 1 set source files
file(GLOB_RECURSE SOURCES LIST_DIRECTORIES true *.h *.cpp)
set (SOURCES ${SOURCES})

# 2 add executable
add_executable(${BINARY}_run ${SOURCES})

# 3 add a static library for the test source 
add_library(${BINARY}_lib STATIC ${SOURCES})