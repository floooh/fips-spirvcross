#
# project: fips-spirvcross
#
set(FIPS_EXCEPTIONS ON CACHE BOOL "Enable C++ exceptions" FORCE)
if (NOT FIPS_IMPORT)
    cmake_minimum_required(VERSION 2.8)
    get_filename_component(FIPS_ROOT_DIR "../fips" ABSOLUTE)
    include("${FIPS_ROOT_DIR}/cmake/fips.cmake")
    fips_setup(PROJECT spirvcross)
endif()
fips_begin_lib(spirvcross)
    fips_dir(SPIRV-Cross)
    fips_files(
        GLSL.std.450.h
        spirv_common.hpp
        spirv.hpp
        spirv_cross.hpp spirv_cross.cpp
        spirv_cfg.hpp spirv_cfg.cpp
        spirv_glsl.hpp spirv_glsl.cpp
        spirv_cpp.hpp spirv_cpp.cpp
        spirv_msl.hpp spirv_msl.cpp
        spirv_hlsl.hpp spirv_hlsl.cpp
    )
fips_end_lib()
fips_finish()


