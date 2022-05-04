cmake_minimum_required(VERSION 3.10)
project(ropesim)

set(CMAKE_CXX_STANDARD 17)


#-------------------------------------------------------------------------------
# Build options
#-------------------------------------------------------------------------------
option(BUILD_LIBCGL "Build with libCGL" ON)


#-------------------------------------------------------------------------------
# Set win32 building flags
#-------------------------------------------------------------------------------
if(MSVC)
    set(MSVC_CXX_FLAGS "-std=gnu++11")

    if(BUILD_DEBUG)
        set(CMAKE_BUILD_TYPE Debug)
    endif()

    set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} ${MSVC_CXX_FLAGS}")
endif(MSVC)

if(MINGW)
    set(MSVC_CXX_FLAGS "-std=gnu++11")

    if(BUILD_DEBUG)
        set(CMAKE_BUILD_TYPE Debug)
    endif()

    set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} ${MSVC_CXX_FLAGS}")
endif(MINGW)


#-------------------------------------------------------------------------------
# Find dependencies
#-------------------------------------------------------------------------------

# Required packages
find_package(OpenGL REQUIRED)
find_package(Threads REQUIRED)

# CGL
if(BUILD_LIBCGL)
    add_subdirectory(CGL)
    include_directories(CGL/include)
else()
	find_package(CGL REQUIRED)
	find_package(GLEW REQUIRED)
	find_package(GLFW REQUIRED)
endif()


#-------------------------------------------------------------------------------
# Add subdirectories
#-------------------------------------------------------------------------------
add_subdirectory(src)

# Install settings
set(CMAKE_INSTALL_PREFIX "${ropesim_SOURCE_DIR}"/)

