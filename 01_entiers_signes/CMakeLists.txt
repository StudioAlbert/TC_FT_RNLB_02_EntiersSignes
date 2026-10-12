add_executable(01_entiers_signes main.cc)
target_include_directories(01_entiers_signes PRIVATE include)

# Avertissements : on veut VOIR les melanges signe / non signe (slide « Melanger »)
if (MSVC)
    target_compile_options(01_entiers_signes PRIVATE /W4 /utf-8)
else ()
    target_compile_options(01_entiers_signes PRIVATE -Wall -Wextra -Wsign-compare)
endif ()

if (SANITIZE AND NOT MSVC)
    target_compile_options(01_entiers_signes PRIVATE -fsanitize=undefined)
    target_link_options(01_entiers_signes PRIVATE -fsanitize=undefined)
endif ()
