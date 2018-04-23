if(WIN32)
	set(SFW_SOURCES
		FileWatcher.cpp
		FileWatcherWin32.cpp
	)	
	add_definitions(-DMINGINE_WIN32)
elseif(UNIX)
	set(SFW_SOURCES 
		FileWatcher.cpp
		FileWatcherLinux.cpp
	)
elseif(APPLE)
	set(SFW_SOURCES 
		FileWatcher.cpp
		FileWatcherOSX.cpp
	)
endif()

add_library(sfw_lib ${SFW_SOURCES})

target_include_directories(sfw_lib PUBLIC
	${SFW_INCLUDE_DIR}
)