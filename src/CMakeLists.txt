cmake_minimum_required(VERSION 3.0.0)

set(SOURCES 
	ssqll.cpp
	${CMAKE_SOURCE_DIR}/include/ssqll/ssqll.h)

add_library(ssqll STATIC ${SOURCES})
target_include_directories(ssqll PUBLIC ${CMAKE_SOURCE_DIR}/include)
target_link_libraries(ssqll sqlite3 ${CMAKE_DL_LIBS})
set_property(TARGET ssqll PROPERTY CXX_STANDARD 14)

install(TARGETS ssqll 
	LIBRARY DESTINATION lib
	ARCHIVE DESTINATION lib)
