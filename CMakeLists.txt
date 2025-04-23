cmake_minimum_required(VERSION 3.10)

project(oauthcpp)

file(GLOB ${PROJECT_NAME}-inc ${PROJECT_SOURCE_DIR}/include/*)
file(GLOB ${PROJECT_NAME}-src ${PROJECT_SOURCE_DIR}/src/*)

add_library(inc${PROJECT_NAME} INTERFACE ${${PROJECT_NAME}-inc})
add_library(lib${PROJECT_NAME} ${${PROJECT_NAME}-src})

target_include_directories(inc${PROJECT_NAME} INTERFACE include)
target_link_libraries(lib${PROJECT_NAME} PUBLIC inc${PROJECT_NAME})
