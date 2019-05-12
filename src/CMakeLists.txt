# Add executable called "GL_exe" that is built from the source files
# The extensions are automatically found.

file(GLOB_RECURSE sources
    "*.c"
)

add_executable(GL_exe ${sources})

# Link to user libraries (if there are any)
if(libraries)
    target_link_libraries(GL_exe ${libraries})
endif()

install( TARGETS GL_exe
    RUNTIME DESTINATION bin
    LIBRARY DESTINATION lib
    ARCHIVE DESTINATION lib/static
)

