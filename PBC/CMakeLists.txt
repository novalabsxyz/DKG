add_library(
  pbc++
  G.cc
  G1.cc
  G2.cc
  GT.cc
  PPPairing.cc
  Pairing.cc
  Zr.cc
  )

target_link_libraries(
  pbc++
  pbc
  )

target_include_directories(
  pbc++
  PUBLIC
  $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
  $<INSTALL_INTERFACE:include>
  )

install(
  TARGETS pbc++
  EXPORT pbc++config
  ARCHIVE  DESTINATION ${CMAKE_INSTALL_LIBDIR}
  LIBRARY  DESTINATION ${CMAKE_INSTALL_LIBDIR}
  RUNTIME  DESTINATION ${CMAKE_INSTALL_BINDIR}
  )

install(
  DIRECTORY include/
  DESTINATION ${CMAKE_INSTALL_INCLUDEDIR}/pbc++
  )

# This makes the project importable from the install directory Put
# config file in per-project dir (name MUST match), can also just go
# into 'cmake'.
install(EXPORT pbc++config DESTINATION share/pbc++/cmake)

# This makes the project importable from the build directory
export(TARGETS pbc++ FILE pbc++config.cmake)
