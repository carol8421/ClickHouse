include (${ClickHouse_SOURCE_DIR}/cmake/add_check.cmake)

foreach (T longjmp siglongjmp)
    add_executable (${T} ${T}.c)
    target_link_libraries (${T} PRIVATE glibc-compatibility)
    if (USE_LIBCXX)
        target_link_libraries (${T} PRIVATE Threads::Threads)
    endif ()
    set_target_properties (${T} PROPERTIES LINKER_LANGUAGE CXX)
    add_check (${T})
endforeach ()
