cmake_minimum_required(VERSION 3.9.3)

project(quickspin_trigger)

# Cmake is searching for OpenCV which is required for some examples. See README for further information.
# option(OpenCV_STATIC "Link with static version of OpenCV without Visual Studio runtime libraries" ON)
# find_package(OpenCV QUIET COMPONENTS core highgui imgproc imgcodecs videoio)

#set up some cxx compiler flags
# enable C++11 support
set(CMAKE_CXX_STANDARD 11)

# add the lib folder to the link path
get_filename_component(QuickSpinAPI_ROOT_DIR ${CMAKE_SOURCE_DIR}/QuickSpinAPI ABSOLUTE)
link_directories(${QuickSpinAPI_ROOT_DIR}/lib)

include_directories(
    SYSTEM
    ${QuickSpinAPI_ROOT_DIR}/include
)

add_executable(${PROJECT_NAME}
    src/main.cpp)

target_link_libraries(${PROJECT_NAME}
    Spinnaker
)

