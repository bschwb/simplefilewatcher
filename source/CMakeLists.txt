if(WIN32)
	set(SFW_SOURCES
		FileWatcher.cpp
		FileWatcherWin32.cpp
	)	
	add_definitions(-DMINGINE_WIN32)
elseif(APPLE)
	set(SFW_SOURCES 
		FileWatcher.cpp
		FileWatcherOSX.cpp
	)
elseif(UNIX)
	set(SFW_SOURCES 
		FileWatcher.cpp
		FileWatcherLinux.cpp
	)
endif()

include_directories(${SFW_INCLUDE_DIR})
add_library(sfw_lib ${SFW_SOURCES})

target_include_directories(sfw_lib PUBLIC
	${SFW_INCLUDE_DIR}
)
