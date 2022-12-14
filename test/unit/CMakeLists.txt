function(create_tests source_list data_files)
   foreach(X ${source_list})
      add_executable("${X}.bin" "${X}.cpp" unit_test_main.cpp ${data_files})
      add_dependencies(tests "${X}.bin")
      target_link_libraries("${X}.bin" mach Catch)
      add_test(NAME "${X}" COMMAND "${X}.bin") 
   endforeach()
endfunction(create_tests)

# for all targets created in this file, include the main dir (containing mach.hpp)
#include_directories(BEFORE ${PROJECT_SOURCE_DIR})

# group together all fluids related tests
set(FLUID_TEST_SRCS
   test_euler_fluxes 
   test_euler_integ
   test_euler_assemble
   test_evolver
   test_inexact_newton
   test_navier_stokes_fluxes
   test_navier_stokes_integ
   test_reconstruction
   test_sbp_fe
   test_viscous_integ
   test_utils
)

create_tests("${FLUID_TEST_SRCS}" euler_test_data.cpp)

