aux_source_directory(./include  DIR_LIB_SRC_INCLUDE)
aux_source_directory(./src  DIR_LIB_SRC)

add_library (glad ${DIR_LIB_SRCS} ${DIR_LIB_SRC_INCLUDE})

