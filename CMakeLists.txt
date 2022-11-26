
include(${MBED_PATH}/tools/cmake/app.cmake)

set(CMAKE_TRY_COMPILE_TARGET_TYPE "STATIC_LIBRARY")
set(MBED_PATH ${PROJECT_SOURCE_DIR}/../os/mbed-os/ CACHE INTERNAL "")
set(MBED_CONFIG_PATH ${CMAKE_CURRENT_BINARY_DIR}/.. CACHE INTERNAL "")

add_library(mcp23s17 MCP23S17.cpp)
target_include_directories(mcp23s17 INTERFACE ${CMAKE_CURRENT_SOURCE_DIR})
target_link_libraries(mcp23s17 mbed-os)
set_target_properties(mcp23s17 PROPERTIES LINKER_LANGUAGE CXX)
