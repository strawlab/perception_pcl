cmake_minimum_required(VERSION 2.4.6)
include($ENV{ROS_ROOT}/core/rosbuild/rosbuild.cmake)
rosbuild_init()
rosbuild_genmsg()

find_package (VTK REQUIRED)
execute_process (COMMAND echo ${VTK_INCLUDE_DIRS} COMMAND sed "s/ / -I/g" OUTPUT_FILE ${PROJECT_SOURCE_DIR}/vtk_include_dirs.txt)
execute_process (COMMAND echo ${VTK_LIBRARY_DIRS} OUTPUT_FILE ${PROJECT_SOURCE_DIR}/vtk_library_dirs.txt)
