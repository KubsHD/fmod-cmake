project(fmod)

add_library(fmod SHARED IMPORTED GLOBAL)

if (WIN32)
set_property(TARGET fmod PROPERTY
             IMPORTED_LOCATION "${CMAKE_CURRENT_SOURCE_DIR}/win/core/lib/x64/fmod.dll")
set_property(TARGET fmod PROPERTY
             IMPORTED_IMPLIB "${CMAKE_CURRENT_SOURCE_DIR}/win/core/lib/x64/fmod_vc.lib")
set_property(TARGET fmod PROPERTY
             INTERFACE_INCLUDE_DIRECTORIES "${CMAKE_CURRENT_SOURCE_DIR}/win/core/inc")
elseif(APPLE)
set_property(TARGET fmod PROPERTY
             IMPORTED_LOCATION "${CMAKE_CURRENT_SOURCE_DIR}/mac/core/lib/libfmod.dylib")
set_property(TARGET fmod PROPERTY
             INTERFACE_INCLUDE_DIRECTORIES "${CMAKE_CURRENT_SOURCE_DIR}/mac/core/inc")
endif()