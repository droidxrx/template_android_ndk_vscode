cmake_minimum_required(VERSION 3.21)

project(template_android_ndk_vscode)

add_executable(${PROJECT_NAME} src/main.cpp)

if(CMAKE_BUILD_TYPE STREQUAL "Release")
    add_custom_command(TARGET ${PROJECT_NAME} POST_BUILD COMMAND ${CMAKE_STRIP} --strip-all $<TARGET_FILE:${PROJECT_NAME}>)
endif()
