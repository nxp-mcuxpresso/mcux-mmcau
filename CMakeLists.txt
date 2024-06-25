
if (CONFIG_MCUX_COMPONENT_middleware.mmcau.cm4_cm7)
    mcux_add_source(
        SOURCES asm-cm4-cm7/lib_mmcau.a,
        TOOLCHAINS armgcc mcux iar
    )
    mcux_add_source(
        SOURCES asm-cm4-cm7/lib_mmcau.lib,
        TOOLCHAINS mdk
    )
    mcux_add_include(
        INCLUDES ./
    )
endif()

if (CONFIG_MCUX_COMPONENT_middleware.mmcau.cm0p)
    mcux_add_source(
        SOURCES asm-cm0p/lib_mmcau-cm0p.a,
        TOOLCHAINS armgcc mcux iar
    )
    mcux_add_source(
        SOURCES asm-cm0p/lib_mmcau-cm0p.lib,
        TOOLCHAINS mdk
    )
    mcux_add_include(
        INCLUDES ./
    )
endif()

if (CONFIG_MCUX_COMPONENT_middleware.mmcau.common_files)
    mcux_add_source(
        SOURCES cau_api.h fsl_mmcau.h fsl_mmcau.c
    )
    mcux_add_include(
        INCLUDES ./
    )
endif()

if (CONFIG_MCUX_COMPONENT_middleware.mmcau.mmcau_files)
    mcux_add_source(
        SOURCES *.txt
    )
    mcux_add_source(
        SOURCES asm-cm0p/src/*.hdr,
        CORES cm0p
    )
    mcux_add_source(
        SOURCES asm-cm0p/src/*.s,
        CORES cm0p
    )
    mcux_add_source(
        SOURCES asm-cm4-cm7/src/*.hdr,
        CORES cm4 cm4f cm7f
    )
    mcux_add_source(
        SOURCES asm-cm4-cm7/src/*.s,
        CORES cm4 cm4f cm7f
    )
endif()
