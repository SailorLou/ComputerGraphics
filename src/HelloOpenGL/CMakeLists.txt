cmake_minimum_required (VERSION 3.5)

set(THIS_MODULE_NAME HelloOpenGL)
project (${THIS_MODULE_NAME})

aux_source_directory(. DIR_SRCS)

find_package(OpenGL REQUIRED)

include_directories(${CMAKE_SOURCE_DIR}/ThirdParty/glad/include 
                    ${CMAKE_SOURCE_DIR}/ThirdParty/glfw/include)

set(LIBS glfw3  ${OPENGL_LIBRARIES} glad)

include_directories(${OPENGL_INCLUDE_DIR})
link_directories(${CMAKE_ARCHIVE_OUTPUT_DIRECTORY_DEBUG})
link_directories(${CMAKE_ARCHIVE_OUTPUT_DIRECTORY_RELEASE})   	

add_executable(${THIS_MODULE_NAME} ${DIR_SRCS})

TARGET_LINK_LIBRARIES(${THIS_MODULE_NAME} ${LIBS} ${EXTRA_LIBS})

install(TARGETS ${THIS_MODULE_NAME}
        RUNTIME DESTINATION bin
        LIBRARY DESTINATION lib
        ARCHIVE DESTINATION lib/static)
