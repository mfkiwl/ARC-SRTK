if(enable-qt5)
	find_package(Qt5Gui QUIET)
	if(Qt5Gui_FOUND)
		get_target_property(mgl_qt_loc Qt5::QWindowsIntegrationPlugin LOCATION)
	endif(Qt5Gui_FOUND)
endif(enable-qt5)

install(CODE "SET(mgl_qt_loc \"${mgl_qt_loc}\")")
install(CODE "SET(CMAKE_INSTALL_PREFIX \"${CMAKE_INSTALL_PREFIX}\")")
install(SCRIPT install-deps.txt)
