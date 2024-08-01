# The tools are not shared libraries
add_definitions(-DCPL_DISABLE_DLL)

set(TOOL_TARGETS commander ctb  ${CMAKE_THREAD_LIBS_INIT})

# Add the `mjp-tile` executable
add_executable(mjp-tile mjp-tile.cpp)
target_link_libraries(mjp-tile ${TOOL_TARGETS})

# Add the `mjp-export` executable
add_executable(mjp-export mjp-export.cpp)
target_link_libraries(mjp-export ${TOOL_TARGETS})

# Add the `ctb-info` executable
add_executable(mjp-info mjp-info.cpp)
target_link_libraries(mjp-info ${TOOL_TARGETS})

# Add the `ctb-extents` executable
add_executable(mjp-extents mjp-extents.cpp)
target_link_libraries(mjp-extents ${TOOL_TARGETS})

# Install the tools
set(TOOLS mjp-tile mjp-export mjp-info mjp-extents)
install(TARGETS ${TOOLS} DESTINATION bin)
