############################################################################
# CMakeLists.txt file for building ROOT sql/pgsql package
############################################################################

ROOT_STANDARD_LIBRARY_PACKAGE(PgSQL
  HEADERS
    TPgSQLResult.h
    TPgSQLRow.h
    TPgSQLServer.h
    TPgSQLStatement.h
  SOURCES
    src/TPgSQLResult.cxx
    src/TPgSQLRow.cxx
    src/TPgSQLServer.cxx
    src/TPgSQLStatement.cxx
  DICTIONARY_OPTIONS
    -I${POSTGRESQL_INCLUDE_DIR}
  DEPENDENCIES
    Core
    Net
    RIO
)

target_include_directories(PgSQL PUBLIC ${POSTGRESQL_INCLUDE_DIR})
target_link_libraries(PgSQL PUBLIC ${POSTGRESQL_LIBRARIES})
