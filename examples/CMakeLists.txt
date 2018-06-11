add_executable(example example.c)
add_dependencies(example hiredis)
target_link_libraries(example hiredis)
