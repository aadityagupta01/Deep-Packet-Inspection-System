cmake_minimum_required(VERSION 3.16)
project(PacketAnalyzer VERSION 1.0)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

# DPI engine sources
set(SOURCES
    src/dpi_mt.cpp
    src/pcap_reader.cpp
    src/packet_parser.cpp
    src/sni_extractor.cpp
    src/types.cpp
)

find_package(Threads REQUIRED)

add_executable(dpi_engine ${SOURCES})
target_include_directories(dpi_engine PRIVATE ${CMAKE_SOURCE_DIR}/include)
target_link_libraries(dpi_engine PRIVATE Threads::Threads)
