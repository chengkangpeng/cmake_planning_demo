project(planning_main)

#添加子目录
add_subdirectory(process)
add_subdirectory(pnc_map)

#添加可执行文件
add_executable(${PROJECT_NAME} planning_main.cpp)

#添加包含目录
target_include_directories(${PROJECT_NAME}
PUBLIC
${PROCESS_DIR}
)

#链接动态库
target_link_libraries(${PROJECT_NAME}
PUBLIC
process
)