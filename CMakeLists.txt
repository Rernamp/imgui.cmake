

set(ImguiFolder ${CMAKE_CURRENT_SOURCE_DIR}/imgui)

add_library(Imgui INTERFACE)

target_include_directories(Imgui INTERFACE
    ${ImguiFolder}
)

target_sources(Imgui INTERFACE
    ${ImguiFolder}/imconfig.h
    ${ImguiFolder}/imgui.cpp
    ${ImguiFolder}/imgui.h
    ${ImguiFolder}/imgui_demo.cpp
    ${ImguiFolder}/imgui_draw.cpp
    ${ImguiFolder}/imgui_internal.h
    ${ImguiFolder}/imgui_tables.cpp
    ${ImguiFolder}/imgui_widgets.cpp
    ${ImguiFolder}/imstb_rectpack.h
    ${ImguiFolder}/imstb_textedit.h
    ${ImguiFolder}/imstb_truetype.h
)

add_library(ImguiBackendWin32 INTERFACE)
add_library(ImguiBackendDx10 INTERFACE)

target_include_directories(ImguiBackendWin32 INTERFACE
    ${ImguiFolder}/backends
)

target_include_directories(ImguiBackendDx10 INTERFACE
    ${ImguiFolder}/backends
)

target_sources(ImguiBackendWin32 INTERFACE
    ${ImguiFolder}/backends/imgui_impl_win32.cpp
    ${ImguiFolder}/backends/imgui_impl_win32.h
)

target_sources(ImguiBackendDx10 INTERFACE
    ${ImguiFolder}/backends/imgui_impl_dx10.cpp
    ${ImguiFolder}/backends/imgui_impl_dx10.h
)