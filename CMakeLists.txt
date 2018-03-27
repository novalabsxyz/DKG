cmake_minimum_required(VERSION 3.2 FATAL_ERROR)
project(DKG CXX)

# Must use GNUInstallDirs to install libraries into correct locations
# on all platforms.
include(GNUInstallDirs)

add_subdirectory(PBC)
add_subdirectory(src)


# /usr/local/include/Zr.h
# /usr/local/include/PBCExceptions.h
# /usr/local/include/Pairing.h
# /usr/local/include/G2.h
# /usr/local/include/PBC.h
# /usr/local/include/G.h
# /usr/local/include/G1.h
# /usr/local/include/GT.h
