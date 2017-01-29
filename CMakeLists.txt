cmake_minimum_required(VERSION 3.2)

project(pillow VERSION 4.1.0 LANGUAGES C)

if(MSVC)
  set(CMAKE_DEBUG_POSTFIX "d")
endif()

find_package(python REQUIRED NO_MODULE)
find_package(openjpeg REQUIRED NO_MODULE)
find_package(zlib REQUIRED NO_MODULE)

add_library(pillow
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/BitDecode.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/Blend.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/BoxBlur.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/Chops.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/codec_fd.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/Convert.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/ConvertYCbCr.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/Copy.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/Crc32.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/Crop.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/Dib.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/Draw.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/Effects.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/EpsEncode.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/Except.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/File.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/Fill.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/Filter.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/FliDecode.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/Geometry.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/GetBBox.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/Gif.h
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/GifDecode.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/GifEncode.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/HexDecode.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/Histo.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/Imaging.h
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/ImDib.h
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/ImPlatform.h
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/Jpeg.h
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/Jpeg2K.h
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/Jpeg2KDecode.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/Jpeg2KEncode.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/JpegDecode.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/JpegEncode.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/Lzw.h
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/LzwDecode.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/Matrix.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/ModeFilter.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/MspDecode.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/Negative.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/Offset.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/Pack.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/PackDecode.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/Palette.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/Paste.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/PcdDecode.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/PcxDecode.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/PcxEncode.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/Point.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/Quant.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/QuantHash.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/QuantHash.h
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/QuantHeap.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/QuantHeap.h
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/QuantOctree.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/QuantOctree.h
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/QuantPngQuant.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/QuantPngQuant.h
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/QuantTypes.h
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/RankFilter.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/Raw.h
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/RawDecode.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/RawEncode.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/Resample.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/Storage.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/SunRleDecode.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/TgaRleDecode.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/TiffDecode.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/TiffDecode.h
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/Unpack.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/UnpackYCC.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/UnsharpMask.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/XbmDecode.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/XbmEncode.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/Zip.h
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/ZipDecode.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/ZipEncode.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/Access.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/AlphaComposite.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/Bands.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/BcnDecode.c
    ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/Bit.h
    ${CMAKE_CURRENT_SOURCE_DIR}/_imaging.c
    ${CMAKE_CURRENT_SOURCE_DIR}/_imagingmath.c
    ${CMAKE_CURRENT_SOURCE_DIR}/_imagingmorph.c
    ${CMAKE_CURRENT_SOURCE_DIR}/_webp.c
    ${CMAKE_CURRENT_SOURCE_DIR}/decode.c
    ${CMAKE_CURRENT_SOURCE_DIR}/display.c
    ${CMAKE_CURRENT_SOURCE_DIR}/encode.c
    ${CMAKE_CURRENT_SOURCE_DIR}/map.c
    ${CMAKE_CURRENT_SOURCE_DIR}/outline.c
    ${CMAKE_CURRENT_SOURCE_DIR}/path.c
)

target_link_libraries(pillow
  PRIVATE
  python::python
  openjpeg::openjpeg
  zlib::zlibstatic
)

target_include_directories(pillow
  PRIVATE
  $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/libImaging>
  INTERFACE
  $<INSTALL_INTERFACE:include>
  PUBLIC
  $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/libImaging>
)

target_compile_definitions(pillow
  PRIVATE
  _CRT_SECURE_NO_WARNINGS
  _CRT_STDC_NO_DEPRECATE
  HAVE_LIBZ
)

include(CMakePackageConfigHelpers)
write_basic_package_version_file(
  ${CMAKE_CURRENT_BINARY_DIR}/${PROJECT_NAME}-config-version.cmake
  VERSION ${PROJECT_VERSION}
  COMPATIBILITY AnyNewerVersion
)

install(TARGETS ${PROJECT_NAME} EXPORT ${PROJECT_NAME}
  RUNTIME DESTINATION bin
  ARCHIVE DESTINATION lib
  LIBRARY DESTINATION lib
)

# install(FILES
#   ${CMAKE_CURRENT_SOURCE_DIR}/libImaging/*.h
#   DESTINATION include
# )

install(EXPORT ${PROJECT_NAME}
  FILE
  ${PROJECT_NAME}.cmake
  NAMESPACE
    ${PROJECT_NAME}::
  DESTINATION
    lib/cmake/${PROJECT_NAME}
)

install(FILES
  cmake/${PROJECT_NAME}-config.cmake
  ${CMAKE_CURRENT_BINARY_DIR}/${PROJECT_NAME}-config-version.cmake
  DESTINATION
    lib/cmake/${PROJECT_NAME}
)

export(TARGETS ${PROJECT_NAME}
  FILE
  ${CMAKE_CURRENT_BINARY_DIR}/${PROJECT_NAME}-config.cmake
  NAMESPACE ${PROJECT_NAME}::
)
