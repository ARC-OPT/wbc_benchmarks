pkg_search_module(wbc-robot_models-pinocchio REQUIRED IMPORTED_TARGET wbc-robot_models-pinocchio)
pkg_search_module(wbc-robot_models-kdl REQUIRED IMPORTED_TARGET wbc-robot_models-kdl)
pkg_search_module(wbc-robot_models-hyrodyn REQUIRED IMPORTED_TARGET wbc-robot_models-hyrodyn)
pkg_search_module(wbc-robot_models-rbdl REQUIRED IMPORTED_TARGET wbc-robot_models-rbdl)
pkg_search_module(wbc-core REQUIRED IMPORTED_TARGET wbc-core)

include_directories(${wbc-core_INCLUDE_DIRS})

add_executable(benchmark_robot_models benchmark_robot_models.cpp ../benchmarks_common.cpp)
target_link_libraries(benchmark_robot_models
                      PkgConfig::wbc-robot_models-kdl
                      PkgConfig::wbc-robot_models-hyrodyn
                      PkgConfig::wbc-robot_models-pinocchio
                      PkgConfig::wbc-robot_models-rbdl
                      PkgConfig::wbc-core
                      ${Boost_LIBRARIES})

