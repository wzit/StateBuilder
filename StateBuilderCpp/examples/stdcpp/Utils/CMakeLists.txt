set(SMSTDUTILS_LIBRARY fsmstd CACHE INTERNAL "SMSTDUTILS LIBRARY NAME")
set(SMSTDUTILS_INCLUDE_DIR ${CMAKE_CURRENT_SOURCE_DIR} CACHE INTERNAL "SMSTDUTILS INCLUDE DIRECTORY")

set(FSM_STD_SRC
  ObserverStd.cpp
)

find_package(STATEBUILDERCPP REQUIRED)

include_directories(${STATEBUILDERCPP_INCLUDE_DIR})

add_library(${SMSTDUTILS_LIBRARY} STATIC ${FSM_STD_SRC} ) 

# A warning is an error
if(MSVC) 
  ADD_DEFINITIONS( /W4 ) 
else (MSVC)  
  ADD_DEFINITIONS( -Wall -Werror )
endif (MSVC)

