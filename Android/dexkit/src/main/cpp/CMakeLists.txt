cmake_minimum_required(VERSION 3.4.1)
project(dexkit)

find_package(cxx REQUIRED CONFIG)
link_libraries(cxx::cxx)

add_subdirectory(../../../../../Core Core)

add_library(${PROJECT_NAME} SHARED
        native-bridge.cpp)

find_library(log-lib log)

target_link_libraries(${PROJECT_NAME}
        dex_kit_static
        z
        ${log-lib})
