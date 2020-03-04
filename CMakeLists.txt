# tsah dudes.
# before using this, set the variables "ImGui-SFML-Include-ImGui" and "ImGui-SFML-Include-SFML"
# to the respective directories that you can include SFML and ImGui from.

cmake_minimum_required(VERSION 3.1)

project(imgui-sfml
  LANGUAGES CXX
  VERSION 2.1
)

set(Headers
	${CMAKE_CURRENT_LIST_DIR}/Include/imconfig-sfml.h
	${CMAKE_CURRENT_LIST_DIR}/Include/imgui-sfml.h
	${CMAKE_CURRENT_LIST_DIR}/Include/imgui-sfml_export.h
)

add_library(${PROJECT_NAME} ${Headers} ${CMAKE_CURRENT_LIST_DIR}/Source/imgui-sfml.cpp)
target_link_libraries(${PROJECT_NAME} PUBLIC sfml-graphics sfml-system sfml-window)
target_include_directories(${PROJECT_NAME} PUBLIC 
	${CMAKE_CURRENT_LIST_DIR}/Include
	${ImGui-SFML-Include-ImGui}
	${ImGui-SFML-Include-SFML}
)
