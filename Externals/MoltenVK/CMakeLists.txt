include(ExternalProject)

set(MOLTENVK_VERSION "v1.1.5")

ExternalProject_Add(MoltenVK
  GIT_REPOSITORY https://github.com/KhronosGroup/MoltenVK.git
  GIT_TAG ${MOLTENVK_VERSION}

  CONFIGURE_COMMAND ${CMAKE_CURRENT_LIST_DIR}/configure.sh <LOG_DIR> <SOURCE_DIR> ${MOLTENVK_VERSION}

  BUILD_COMMAND make -C <SOURCE_DIR> macos
  BUILD_IN_SOURCE ON
  BUILD_BYPRODUCTS <SOURCE_DIR>/Package/Release/MoltenVK/dylib/macOS/libMoltenVK.dylib

  INSTALL_COMMAND ""

  LOG_CONFIGURE ON
  LOG_BUILD ON
  LOG_OUTPUT_ON_FAILURE ON
)
