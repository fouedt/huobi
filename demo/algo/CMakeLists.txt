cmake_minimum_required(VERSION 3.10...3.17)
project(account LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)

set(cpprestsdk_DIR /usr/lib/${CMAKE_LIBRARY_ARCHITECTURE}/cmake/)

include_directories(/usr/local/huobi)

find_package(cpprestsdk REQUIRED)

link_directories(/usr/local/lib/)
link_directories(/usr/local/huobi/)

ADD_EXECUTABLE(algodemo ./algodemo.cpp)

target_link_libraries(algodemo huobi curl ssl crypto cpprestsdk::cpprest z)
