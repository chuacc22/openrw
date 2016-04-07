###########################################################
##      RWLIB
###########################################################
SET(RWLIB_SOURCES

	# GL stuff is only here temporarily, hoping to move it back to rwengine
	"source/gl/gl_core_3_3.c"
	"source/gl/gl_core_3_3.h"
	"source/gl/DrawBuffer.hpp"
	"source/gl/DrawBuffer.cpp"
	"source/gl/GeometryBuffer.hpp"
	"source/gl/GeometryBuffer.cpp"
	"source/gl/TextureData.hpp"
	"source/gl/TextureData.cpp"

	"source/rw/types.hpp"

	"source/platform/FileHandle.hpp"
	"source/platform/FileIndex.hpp"
	"source/platform/FileIndex.cpp"

	"source/data/ResourceHandle.hpp"
	"source/data/Model.hpp"
	"source/data/Model.cpp"

	"source/loaders/LoaderIMG.hpp"
	"source/loaders/LoaderIMG.cpp"
	"source/loaders/RWBinaryStream.hpp"
	"source/loaders/LoaderDFF.hpp"
	"source/loaders/LoaderDFF.cpp"
	"source/loaders/LoaderTXD.hpp"
	"source/loaders/LoaderTXD.cpp"

	"source/job/WorkContext.hpp"
	"source/job/WorkContext.cpp"
	)

add_library(rwlib

	${RWLIB_SOURCES}
	)

include_directories(
	"${CMAKE_CURRENT_SOURCE_DIR}/source")

target_include_directories(rwlib
	PUBLIC "${CMAKE_CURRENT_SOURCE_DIR}/source")

target_link_libraries(rwlib
	${OPENGL_LIBRARIES}
	${OPENRW_PLATFORM_LIBS})