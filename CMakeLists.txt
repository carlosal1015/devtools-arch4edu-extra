cmake_minimum_required(VERSION 3.19)
project(devtools-arch4edu-extra)

add_subdirectory(config)
add_subdirectory(keyring)

# file(GLOB_RECURSE ymerge_FILES src/ymerge/*)

# install(TARGETS ymerge youtil auracle libauracle)

# install(FILES extra/bash_completion
#     RENAME auracle
#     DESTINATION ${CMAKE_INSTALL_DATADIR}/bash-completion/completions
# )