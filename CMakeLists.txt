cmake_minimum_required(VERSION 3.4)
project(formatter_ci)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_library(formatter STATIC formatter_lib/sources/formatter.cpp)
target_include_directories(formatter PUBLIC formatter_lib/include)

add_library(formatter_ex STATIC formatter_ex_lib/ex.cpp)
target_include_directories(formatter_ex PUBLIC formatter_ex_lib formatter_lib/include)
target_link_libraries(formatter_ex formatter)

add_library(solver_lib STATIC solver_lib/calc.cc)
target_include_directories(solver_lib PUBLIC solver_lib)

add_executable(hello_world hello_world_application/run.cc)
target_link_libraries(hello_world formatter_ex)

add_executable(solver solver_application/app.cc)
target_link_libraries(solver solver_lib formatter_ex)

install(TARGETS formatter formatter_ex solver_lib hello_world solver
        ARCHIVE DESTINATION lib
        RUNTIME DESTINATION bin)
