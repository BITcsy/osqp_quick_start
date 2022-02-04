cmake_minimum_required(VERSION 3.8 FATAL_ERROR)
project(OsqpEigen-Try)

# dependences & Library target
find_package(OsqpEigen)
find_package(Eigen3)
find_package(PythonLibs 3.6)
 
# Examples

include_directories(SYSTEM ${EIGEN3_INCLUDE_DIR})
include_directories(${CMAKE_CURRENT_SOURCE_DIR} "/home/csy/.local/lib/python3.6/site-packages/numpy/core/include")
# include_directories("/mnt/d/linux_workspace/csy1_workspace/src" "/home/csy/.local/lib/python3.6/site-packages/numpy/core/include")
add_executable(osqp_try osqp_try.cpp)
target_include_directories(osqp_try PRIVATE ${PYTHON_INCLUDE_DIRS})
target_link_libraries(osqp_try ${PYTHON_LIBRARIES} OsqpEigen::OsqpEigen)

# target_link_libraries(minimal PRIVATE matplotlib_cpp)
# set_target_properties(minimal PROPERTIES RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/bin")


