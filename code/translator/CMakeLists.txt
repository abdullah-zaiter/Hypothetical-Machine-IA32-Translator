cmake_minimum_required(VERSION 3.0.0)
project(Hypothetical-Machine-IA32-Translator VERSION 0.1.0)

include(CTest)
enable_testing()
set (CMAKE_CXX_STANDARD 11)
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/libbin)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/libbin)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}./../bin)

include_directories(include)
add_library (translator STATIC lib/translator.cpp)

add_library (preprocessor STATIC lib/preprocessor.cpp)

add_executable(main src/main.cpp)
TARGET_LINK_LIBRARIES(main translator preprocessor)



include(CPack)
