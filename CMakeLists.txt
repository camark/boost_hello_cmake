cmake_minimum_required(VERSION 3.8)
project(boost1)

set(CMAKE_CXX_STANDARD 17)
find_package(Boost REQUIRED COMPONENTS
        # regex
        timer   # 我的工程中只使用了 boost 的 filesystem 功能,因此这里只有一个组件
        )
if(NOT Boost_FOUND)
    message("Not found Boost")
endif()

set(SOURCE_FILES main.cpp)
add_executable(boost1 ${SOURCE_FILES})
target_link_libraries(boost1 ${Boost_LIBRARIES})