cmake_minimum_required(VERSION 2.17)

project(DepthFromFocus)
set(PROJECT_VERSIOIN_MAJOR 0)
set(PROJECT_VERSION_MINOR 1)
set (CMAKE_CXX_STANDARD 11)

include_directories(/usr/local/Cellar/opencv/4.5.0/include/opencv4)
link_directories(/usr/local/Cellar/opencv/4.5.0/lib/)

set(EXT_LIBS opencv_core opencv_highgui opencv_imgproc opencv_calib3d opencv_features2d opencv_ximgproc opencv_imgcodecs)

set( CMAKE_INSTALL_PREFIX ../ )

add_executable(
	DepthFromFocus
	
	# Header Files
	include/block.h
	include/energy.h
	include/GCoptimization.h
	include/graph.h
	include/LinkedBlockList.h

	# Source Files
	src/main.cpp
	src/example.cpp
	src/GCoptimization.cpp
	src/graph.cpp
	src/LinkedBlockList.cpp
	src/maxflow.cpp
)

target_link_libraries(DepthFromFocus ${EXT_LIBS})


