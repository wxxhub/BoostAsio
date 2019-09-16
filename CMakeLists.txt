cmake_minimum_required(VERSION 3.0)
project(boost_asio)

find_package(Boost REQUIRED system)

if (NOT Boost_FOUND)
    message("Not found Boost!")
endif()

add_executable(server src/server.cpp)
target_link_libraries(server ${Boost_LIBRARIES})

add_executable(client src/client.cpp)
target_link_libraries(client ${Boost_LIBRARIES} boost_thread)

add_executable(server2 src/server2.cpp)
target_link_libraries(server ${Boost_LIBRARIES} boost_thread)