cmake_minimum_required (VERSION 2.8)
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
project ( LBE_DEMO )
include_directories ( src/lbe src/slic )
find_package ( OpenCV REQUIRED )
add_executable ( demo src/lbe/main.cpp )
add_library ( LBE src/lbe/lbe.cpp src/lbe/superpixels.cpp )
add_library ( SLIC src/slic/SLIC.cpp )
target_link_libraries( demo LBE SLIC ${OpenCV_LIBS} )
# configure_file(script/demo.sh demo.sh COPYONLY)
