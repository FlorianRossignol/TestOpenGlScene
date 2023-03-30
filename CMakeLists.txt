cmake_minimum_required (VERSION 3.18)
project(OpenGlTestSCene)

set (CMAKE_CXX_STANDARD 20)
set (CMAKE_CXX_STANDARD_REQUIRED ON)

set_property(GLOBAL PROPERTY USE_FOLDERS ON)

find_package(GLEW REQUIRED)
find_package(glm CONFIG REQUIRED)
find_package(SDL2 CONFIG REQUIRED)
find_package(imgui CONFIG REQUIRED)
find_package(assimp CONFIG REQUIRED)
find_package(fmt CONFIG REQUIRED)
find_package(stb CONFIG)


file(GLOB_RECURSE src/*.cpp include/*.h)



add_executable(main main/OpenGlTestScene.cpp)

target_include_directories(main PUBLIC include/ ${STB_INCLUDE_DIRS})
target_link_libraries(main PUBLIC GLEW::GLEW glm::glm SDL2::SDL2 SDL2::SDL2main imgui::imgui assimp::assimp fmt::fmt)



