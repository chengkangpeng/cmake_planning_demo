project(planning_main)

#添加子目录
add_subdirectory(process)
add_subdirectory(pnc_map)
add_subdirectory(show_result)

#添加可执行文件
add_executable(${PROJECT_NAME} planning_main.cpp)

#添加包含目录
target_include_directories(${PROJECT_NAME}
PUBLIC
${PROCESS_DIR}
)
target_include_directories(${PROJECT_NAME}
PUBLIC
${SHOW_RESULT_DIR}
)

#链接动态库
target_link_libraries(${PROJECT_NAME}
PUBLIC
process
)
target_link_libraries(${PROJECT_NAME}
PUBLIC
show_result
)
