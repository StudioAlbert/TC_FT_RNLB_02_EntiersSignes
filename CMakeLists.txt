cmake_minimum_required(VERSION 3.28)
project(TC_FT_RNLB_02_EntiersSignes CXX)

set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

# Detecteur de comportements indefinis (GCC / Clang, hors Windows) :
#   cmake -S . -B build -DSANITIZE=ON
option(SANITIZE "Active -fsanitize=undefined" OFF)

add_subdirectory(01_entiers_signes)
