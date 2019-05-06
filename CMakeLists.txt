cmake_minimum_required(VERSION 3.14)

set(ProjectName console_app_al2o3_template)
project(${ProjectName})

include(FetchContent)
FetchContent_Declare( al2o3 GIT_REPOSITORY https://github.com/DeanoC/al2o3 GIT_TAG master )
FetchContent_GetProperties(al2o3)
FetchContent_Populate(al2o3)
add_subdirectory(${al2o3_SOURCE_DIR} ${al2o3_BINARY_DIR})

set(Src main.c)
set(Deps al2o3_platform)
ADD_CONSOLE_APP(${ProjectName} "${Src}" "${Deps}")
