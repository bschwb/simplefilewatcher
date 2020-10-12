cmake_minimum_required(VERSION 3.2 FATAL_ERROR)

if (WIN32)
	set(
		SFW_SOURCES
		"${CMAKE_CURRENT_SOURCE_DIR}/FileWatcher.cpp"
		"${CMAKE_CURRENT_SOURCE_DIR}/FileWatcherWin32.cpp"
	)
ELSEIF(APPLE)
	set(
		SFW_SOURCES
		"${CMAKE_CURRENT_SOURCE_DIR}/FileWatcher.cpp"
		"${CMAKE_CURRENT_SOURCE_DIR}/FileWatcherOSX.cpp"
	)
ELSEIF(UNIX)
	set(
		SFW_SOURCES
		"${CMAKE_CURRENT_SOURCE_DIR}/FileWatcher.cpp"
		"${CMAKE_CURRENT_SOURCE_DIR}/FileWatcherLinux.cpp"
	)
ENDIF()

include_directories(${SFW_INCLUDE_DIR})
add_library(sfw_lib ${SFW_SOURCES})
