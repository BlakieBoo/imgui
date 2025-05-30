SET(imgui_PATH ${CMAKE_CURRENT_SOURCE_DIR})

if(NOT EXISTS "${imgui_PATH}/imgui.h")
	message(FATAL_ERROR "Imgui not found. Did you forget to init the submodules?")
endif()

file(GLOB imgui_CPP
	"${imgui_PATH}/*.cpp"
)

add_library(imgui
	${imgui_CPP}
)

target_include_directories(imgui PUBLIC
	"${imgui_PATH}"
	"${imgui_PATH}/backends"
	config
)
