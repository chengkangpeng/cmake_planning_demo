cmake_minimum_required(VERSION 3.20.0)#cmake版本
project(planning
    VERSION 0.0.1
    DESCRIPTION "a demo for cmake planning"
    HOMEPAGE_URL "https://github.com/chengkangpeng/cmake_planning_demo"
    LANGUAGES CXX
)

set(CMAKE_CXX_STANDARD 17)
enable_testing()

#变量设置
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/bin)
set(PROCESS_DIR ${CMAKE_SOURCE_DIR}/src/process)
set(PNC_MAP_DIR ${CMAKE_SOURCE_DIR}/src/pnc_map)
set(SHOW_RESULT_DIR ${CMAKE_SOURCE_DIR}/src/show_result)

#第三方库
set(EIGEN3_INCLUDE_DIR "C:/Users/CKP/AppData/Local/Programs/eigen-3.4.0")
list(APPEND CMAKE_MODULE_PATH "${EIGEN3_INCLUDE_DIR}/cmake")

find_package(Eigen3 3.4 REQUIRED)

#添加子目录
add_subdirectory(src)
add_subdirectory(test/map_test)