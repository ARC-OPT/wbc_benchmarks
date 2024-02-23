pkg_search_module(wbc-robot_models-pinocchio REQUIRED IMPORTED_TARGET wbc-robot_models-pinocchio)
pkg_search_module(wbc-robot_models-kdl REQUIRED IMPORTED_TARGET wbc-robot_models-kdl)
pkg_search_module(wbc-robot_models-hyrodyn REQUIRED IMPORTED_TARGET wbc-robot_models-hyrodyn)
pkg_search_module(wbc-robot_models-rbdl REQUIRED IMPORTED_TARGET wbc-robot_models-rbdl)
pkg_search_module(wbc-solvers-qpoases REQUIRED IMPORTED_TARGET wbc-solvers-qpoases)
pkg_search_module(wbc-solvers-qpswift REQUIRED IMPORTED_TARGET wbc-solvers-qpswift)
pkg_search_module(wbc-solvers-eiquadprog REQUIRED IMPORTED_TARGET wbc-solvers-eiquadprog)
pkg_search_module(wbc-solvers-proxqp REQUIRED IMPORTED_TARGET wbc-solvers-proxqp)
pkg_search_module(wbc-scenes-acceleration REQUIRED IMPORTED_TARGET wbc-scenes-acceleration)
pkg_search_module(wbc-scenes-velocity REQUIRED IMPORTED_TARGET wbc-scenes-velocity)
pkg_search_module(wbc-scenes-velocity_qp REQUIRED IMPORTED_TARGET wbc-scenes-velocity_qp)
pkg_search_module(wbc-scenes-acceleration_tsid REQUIRED IMPORTED_TARGET wbc-scenes-acceleration_tsid)
pkg_search_module(wbc-scenes-acceleration_reduced_tsid REQUIRED IMPORTED_TARGET wbc-scenes-acceleration_reduced_tsid)
pkg_search_module(wbc-core REQUIRED IMPORTED_TARGET wbc-core)

add_executable(benchmark_scenes benchmark_scenes.cpp ../benchmarks_common.cpp)
target_link_libraries(benchmark_scenes
                      PkgConfig::wbc-solvers-qpoases
                      PkgConfig::wbc-solvers-qpswift
                      PkgConfig::wbc-solvers-eiquadprog
                      PkgConfig::wbc-solvers-proxqp
                      PkgConfig::wbc-robot_models-kdl
                      PkgConfig::wbc-robot_models-hyrodyn
                      PkgConfig::wbc-robot_models-rbdl
                      PkgConfig::wbc-robot_models-pinocchio
                      PkgConfig::wbc-scenes-acceleration
                      PkgConfig::wbc-scenes-velocity
                      PkgConfig::wbc-scenes-velocity_qp
                      PkgConfig::wbc-scenes-acceleration_tsid
                      PkgConfig::wbc-scenes-acceleration_reduced_tsid
                      Boost::system
                      Boost::filesystem)

