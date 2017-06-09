CMAKE_MINIMUM_REQUIRED(VERSION 2.8)

include(RezBuild)

rez_find_packages(PREFIX pkgs AUTO)

find_python_source(
    VAR sources
)

add_python_egg(
    ${sources}
    EGG_NAME usd_qt_components
    EGG_VERSION ${REZ_BUILD_PROJECT_VERSION}
    DESTINATION python
    LOCAL_SYMLINK
)

add_custom_target(build_egg ALL DEPENDS egg_build)

