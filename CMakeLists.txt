cmake_minimum_required(VERSION 3.16)
project(WeaselTestApp LANGUAGES CXX)
add_executable(WeaselTestApp main.cpp)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

include_directories(${CONAN_INCLUDE_DIRS_JSONCPP})
find_package(jsoncpp REQUIRED)

include_directories(${jsoncpp_INCLUDE_DIRS})

enable_testing()
add_subdirectory(weasel)
target_link_libraries(WeaselTestApp PRIVATE Weasel JsonCpp::JsonCpp)
