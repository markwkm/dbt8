add_subdirectory (pgsql)

set (PROGRAMFILES "")
foreach (FILE dbt8-load-test
              dbt8-plot-results
              dbt8-power-test
              dbt8-run
        )
    configure_file(${FILE}.in ${CMAKE_BINARY_DIR}/${FILE} @ONLY)
    set (PROGRAMFILES ${PROGRAMFILES} ${CMAKE_BINARY_DIR}/${FILE})
endforeach (FILE)

install (PROGRAMS ${PROGRAMFILES} DESTINATION "bin")
