cmake_minimum_required(VERSION 2.8.7)

project(TestCMakeFileInstall)

install(
  FILES "foo.ini"
  DESTINATION bin
  RENAME fooInstalled.ini
  )
  
set(CPACK_MONOLITHIC_INSTALL ON)

if(UNIX)
  set(CPACK_GENERATOR "TGZ")
elseif(WIN32)
  set(CPACK_GENERATOR "NSIS")
endif()

include(CPack)
