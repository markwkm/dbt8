set (PROGRAMFILES "")
foreach (FILE dbt8-pgsql-create-db
              dbt8-pgsql-create-tables
              dbt8-pgsql-drop-tables
              dbt8-pgsql-load-data
              dbt8-pgsql-run-stream
              dbt8-pgsql-start-db
              dbt8-pgsql-stop-db
              dbt8-pgsql-time-statistics
        )
    configure_file(${FILE}.in ${CMAKE_BINARY_DIR}/${FILE} @ONLY)
    set (PROGRAMFILES ${PROGRAMFILES} ${CMAKE_BINARY_DIR}/${FILE})
endforeach (FILE)

install (PROGRAMS ${PROGRAMFILES} DESTINATION "bin")
