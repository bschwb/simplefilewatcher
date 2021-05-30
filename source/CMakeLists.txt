if(WIN32)
	set(SFW_SOURCES
		FileWatcher.cpp
		FileWatcherWin32.cpp
	)	
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

add_library(sfw_lib ${SFW_SOURCES})
target_compile_features(sfw_lib PUBLIC cxx_std_11)
target_include_directories(sfw_lib PUBLIC
	${SFW_INCLUDE_DIR}
)
