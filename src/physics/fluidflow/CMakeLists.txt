target_sources(mach
   PRIVATE
      advection.cpp
      advection.hpp
      euler_fluxes.hpp
      euler_integ_def.hpp
      euler_integ.hpp
      euler.cpp
      euler.hpp
      fluidflow.hpp
      galer_diff.cpp
      galer_diff.hpp
      inviscid_integ_def.hpp
      inviscid_integ.hpp
      navier_stokes_fluxes.hpp
      navier_stokes_integ_def.hpp
      navier_stokes_integ.hpp
      navier_stokes.cpp
      navier_stokes.hpp
      viscous_integ_def.hpp
      viscous_integ.hpp
)

target_include_directories(mach
   PUBLIC
      "${CMAKE_CURRENT_SOURCE_DIR}"
)

