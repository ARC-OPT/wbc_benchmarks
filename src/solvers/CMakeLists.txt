pkg_search_module(wbc-robot_models-pinocchio REQUIRED IMPORTED_TARGET wbc-robot_models-pinocchio)
pkg_search_module(wbc-solvers-qpoases REQUIRED IMPORTED_TARGET wbc-solvers-qpoases)
pkg_search_module(wbc-solvers-qpswift REQUIRED IMPORTED_TARGET wbc-solvers-qpswift)
pkg_search_module(wbc-solvers-proxqp REQUIRED IMPORTED_TARGET wbc-solvers-proxqp)
pkg_search_module(wbc-solvers-eiquadprog REQUIRED IMPORTED_TARGET wbc-solvers-eiquadprog)
pkg_search_module(wbc-scenes-velocity_qp REQUIRED IMPORTED_TARGET wbc-scenes-velocity_qp)
pkg_search_module(wbc-scenes-acceleration_reduced_tsid REQUIRED IMPORTED_TARGET wbc-scenes-acceleration_reduced_tsid)

add_executable(benchmark_solvers benchmark_solvers.cpp ../benchmarks_common.cpp)
target_link_libraries(benchmark_solvers
                      PkgConfig::wbc-solvers-qpoases
                      PkgConfig::wbc-solvers-qpswift
                      PkgConfig::wbc-solvers-eiquadprog
                      PkgConfig::wbc-solvers-proxqp
                      PkgConfig::wbc-robot_models-pinocchio
                      PkgConfig::wbc-scenes-velocity_qp
                      PkgConfig::wbc-scenes-acceleration_reduced_tsid
                      Boost::system
                      Boost::filesystem)

