cmake_minimum_required(VERSION 2.8)

set(GLFW_SOURCE_DIR "external/glfw-3.0.4")
set(GLM_SOURCE_DIR "external/glm-0.9.5.2")

set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "")
set(GLFW_BUILD_TESTS OFF CACHE BOOL "")
set(GLFW_BUILD_DOCS OFF CACHE BOOL "")

set(APP_NAME "OpenGL Minimal App")

add_subdirectory(${GLFW_SOURCE_DIR})

include_directories(${GLFW_SOURCE_DIR}/include
                    ${GLFW_SOURCE_DIR}/deps
                    ${GLM_SOURCE_DIR})

set(GETOPT ${GLFW_SOURCE_DIR}/deps/getopt.h
           ${GLFW_SOURCE_DIR}/deps/getopt.c)

if (APPLE)
    add_executable(${APP_NAME} MACOSX_BUNDLE minimal.cpp)
    set_target_properties(${APP_NAME} PROPERTIES MACOSX_BUNDLE_BUNDLE_NAME ${APP_NAME})
    # target_link_libraries(myapp glfw ${GLFW_LIBRARIES})
    target_link_libraries(${APP_NAME} glfw ${OPENGL_glu_LIBRARY} ${GLFW_LIBRARIES})
endif()

if (APPLE)
    set(BUNDLE_BINARIES ${APP_NAME})

    set_target_properties(${BUNDLE_BINARIES} PROPERTIES
                          MACOSX_BUNDLE_SHORT_VERSION_STRING ${GLFW_VERSION}
                          MACOSX_BUNDLE_LONG_VERSION_STRING ${GLFW_VERSION_FULL})
endif()
