# CMake 最低版本号要求
cmake_minimum_required (VERSION 2.8)
# 项目信息
project (Hello)
# 查找当前目录下的所有源文件
# 并将名称保存到 DIR_SRCS 变量
aux_source_directory(. DIR_SRCS)
# 指定生成目标

find_package(OpenGL REQUIRED)

include_directories(/usr/local/include /usr/local/lib ../../glad/include)
aux_source_directory(../../glad/include GLAD_INCLUDE)

aux_source_directory(../../glad/src GLAD_SRC)

set(LIBS glfw3 X11 Xrandr Xi GL dl pthread )

include_directories(${OPENGL_INCLUDE_DIR})  	

add_executable(Hello ${DIR_SRCS} ${GLAD_INCLUDE} ${GLAD_SRC})

TARGET_LINK_LIBRARIES(Hello ${LIBS} ${EXTRA_LIBS})
