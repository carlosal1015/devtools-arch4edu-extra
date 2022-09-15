set(CONFIG_FILES
  pacman-extra-aarch64.conf
  pacman-extra-armv7h.conf
  arch4edu.conf
)

install(CONFIG_FILES ${HEADERS} DESTINATION ${CMAKE_INSTALL_DATADIR}/devtools)