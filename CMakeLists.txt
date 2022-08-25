cmake_minimum_required(VERSION 3.0.0)
project(TinyWebServer VERSION 0.1.0)

include(CTest)
enable_testing()
include(GNUInstallDirs)

add_executable(TinyWebServer main.cpp  ./timer/lst_timer.cpp ./http/http_conn.cpp ./log/log.cpp ./CGImysql/sql_connection_pool.cpp  webserver.cpp config.cpp)

target_link_libraries(TinyWebServer -lpthread -lmysqlclient)

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)
