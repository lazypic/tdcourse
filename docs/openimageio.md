# OpenImageIO

OpenImageIO는 VFX, 게임, 애니메이션 작업등 제작 파이프라인에서 사용할 수 있는 이미지 컨버팅 도구, API 입니다.
ACES(OpenColorIO)를 지원합니다.

이미지를 컨버팅할 때 사용합니다.
오픈소스로 파이프라인을 구축할 때 굉장히 파워풀한 도구가 됩니다.

### 지원하는 포멧
TIFF, JPEG/JFIF, OpenEXR, PNG, HDR/RGBE, ICO, BMP, Targa, JPEG-2000,
RMan Zfile, FITS, DDS, Softimage PIC, PNM, DPX, Cineon, IFF, Field3D,
OpenVDB, Ptex, Photoshop PSD, Wavefront RLA, SGI, WebP, GIF, DICOM,
많은 디지털카메라의 Raw포멧 등

## 설치
- CentOS7.5
```
# yum install OpenImageIO
# yum install OpenImageIO-utils
```

- macOS
```
$ brew install openimageio
```

- Windows
	- https://github.com/OpenImageIO/oiio/blob/master/INSTALL.md
	- https://sites.google.com/site/openimageio/building-oiio-on-windows

## 컬러 프로파일 로딩 체크
```
$ export OCIO=$HOME/app/OpenColorIO-Configs/aces_1.0.3/config.ocio
```

OCIO를 인식하는지 체크해보겠습니다.
```
$ oiiotool --help
```

아래처럼 컬러스페이스 리스트가 나오면 정상입니다.
```
Known color spaces:

"ACES - ACES2065-1",
"ACES - ACEScc",
"ACES - ACEScct",
"ACES - ACESproxy",
"ACES - ACEScg" (linear),
"Input - ADX - ADX10",
"Input - ADX - ADX16",
"Input - ARRI - V3 LogC (EI160) - Wide Gamut",
"Input - ARRI - V3 LogC (EI200) - Wide Gamut",
"Input - ARRI - V3 LogC (EI250) - Wide Gamut",
"Input - ARRI - V3 LogC (EI320) - Wide Gamut",
"Input - ARRI - V3 LogC (EI400) - Wide Gamut",
"Input - ARRI - V3 LogC (EI500) - Wide Gamut",
"Input - ARRI - V3 LogC (EI640) - Wide Gamut",
"Input - ARRI - V3 LogC (EI800) - Wide Gamut",
"Input - ARRI - V3 LogC (EI1000) - Wide Gamut",
"Input - ARRI - V3 LogC (EI1280) - Wide Gamut",
"Input - ARRI - V3 LogC (EI1600) - Wide Gamut",
"Input - ARRI - V3 LogC (EI2000) - Wide Gamut",
"Input - ARRI - V3 LogC (EI2560) - Wide Gamut",
"Input - ARRI - V3 LogC (EI3200) - Wide Gamut",
"Input - ARRI - Curve - V3 LogC (EI800)",
"Input - ARRI - Linear - ALEXA Wide Gamut",
"Input - Canon - Canon-Log - Rec. 709 Daylight",
"Input - Canon - Canon-Log - Rec. 709 Tungsten",
"Input - Canon - Canon-Log - DCI-P3 Daylight",
"Input - Canon - Canon-Log - DCI-P3 Tungsten",
"Input - Canon - Canon-Log - Cinema Gamut Daylight",
"Input - Canon - Canon-Log - Cinema Gamut Tungsten",
"Input - Canon - Canon-Log - Rec. 2020 Daylight",
"Input - Canon - Canon-Log - Rec. 2020 Tungsten",
"Input - Canon - Canon-Log2 - Rec. 2020 Daylight",
"Input - Canon - Canon-Log2 - Rec. 2020 Tungsten",
"Input - Canon - Canon-Log2 - Cinema Gamut Daylight",
"Input - Canon - Canon-Log2 - Cinema Gamut Tungsten",
"Input - Canon - Canon-Log3 - Rec. 2020 Daylight",
"Input - Canon - Canon-Log3 - Rec. 2020 Tungsten",
"Input - Canon - Canon-Log3 - Cinema Gamut Daylight",
"Input - Canon - Canon-Log3 - Cinema Gamut Tungsten",
"Input - Canon - Curve - Canon-Log",
"Input - Canon - Curve - Canon-Log2",
"Input - Canon - Curve - Canon-Log3",
"Input - Canon - Linear - Canon Rec. 709 Daylight",
"Input - Canon - Linear - Canon Rec. 709 Tungsten",
"Input - Canon - Linear - Canon DCI-P3 Daylight",
"Input - Canon - Linear - Canon DCI-P3 Tungsten",
"Input - Canon - Linear - Canon Cinema Gamut Daylight",
"Input - Canon - Linear - Canon Cinema Gamut Tungsten",
"Input - Canon - Linear - Canon Rec. 2020 Daylight",
"Input - Canon - Linear - Canon Rec. 2020 Tungsten",
"Input - Generic - sRGB - Texture",
"Input - GoPro - Protune Flat - Protune Native - Experimental", "Input - GoPro - Curve - Protune Flat",
"Input - GoPro - Linear - Protune Native - Experimental",
"Input - Panasonic - V-Log - V-Gamut",
"Input - Panasonic - Curve - V-Log",
"Input - Panasonic - Linear - V-Gamut",
"Input - RED - REDlogFilm - DRAGONcolor",
"Input - RED - REDlogFilm - DRAGONcolor2",
"Input - RED - REDlogFilm - REDcolor",
"Input - RED - REDlogFilm - REDcolor2",
"Input - RED - REDlogFilm - REDcolor3",
"Input - RED - REDlogFilm - REDcolor4",
"Input - RED - REDLog3G10 - REDWideGamutRGB",
"Input - RED - Curve - REDlogFilm",
"Input - RED - Curve - REDLog3G10",
"Input - RED - Linear - DRAGONcolor",
"Input - RED - Linear - DRAGONcolor2",
"Input - RED - Linear - REDcolor",
"Input - RED - Linear - REDcolor2",
"Input - RED - Linear - REDcolor3",
"Input - RED - Linear - REDcolor4",
"Input - RED - Linear - REDWideGamutRGB",
"Input - Sony - S-Log1 - S-Gamut",
"Input - Sony - S-Log2 - S-Gamut",
"Input - Sony - S-Log2 - S-Gamut Daylight",
"Input - Sony - S-Log2 - S-Gamut Tungsten",
"Input - Sony - S-Log3 - S-Gamut3.Cine",
"Input - Sony - S-Log3 - S-Gamut3",
"Input - Sony - Curve - S-Log1",
"Input - Sony - Curve - S-Log2",
"Input - Sony - Curve - S-Log3",
"Input - Sony - Linear - S-Gamut",
"Input - Sony - Linear - S-Gamut Daylight",
"Input - Sony - Linear - S-Gamut Tungsten",
"Input - Sony - Linear - S-Gamut3.Cine",
"Input - Sony - Linear - S-Gamut3",
"Output - DCDM (P3 gamut clip)",
"Output - DCDM",
"Output - P3-D60 ST2084 (1000 nits)",
"Output - P3-D60 ST2084 (2000 nits)",
"Output - P3-D60 ST2084 (4000 nits)",
"Output - Rec.2020 ST2084 (1000 nits)",
"Output - P3-D60",
"Output - P3-DCI",
"Output - Rec.2020",
"Output - Rec.709",
"Output - Rec.709 (D60 sim.)",
"Output - sRGB",
"Output - sRGB (D60 sim.)",
"Utility - LMT Shaper",
"Utility - Log2 48 nits Shaper",
"Utility - Log2 48 nits Shaper - AP1",
"Utility - Log2 1000 nits Shaper",
"Utility - Log2 1000 nits Shaper - AP1",
"Utility - Log2 2000 nits Shaper",
"Utility - Log2 2000 nits Shaper - AP1",
"Utility - Log2 4000 nits Shaper",
"Utility - Log2 4000 nits Shaper - AP1",
"Utility - Dolby PQ 10000",
"Utility - Dolby PQ 48 nits Shaper",
"Utility - Dolby PQ 48 nits Shaper - AP1",
"Utility - Dolby PQ 1000 nits Shaper",
"Utility - Dolby PQ 1000 nits Shaper - AP1",
"Utility - Dolby PQ 2000 nits Shaper",
"Utility - Dolby PQ 2000 nits Shaper - AP1",
"Utility - Dolby PQ 4000 nits Shaper",
"Utility - Dolby PQ 4000 nits Shaper - AP1",
"Utility - Curve - Rec.1886",
"Utility - Curve - Rec.2020",
"Utility - Curve - Rec.709",
"Utility - Curve - sRGB",
"Utility - Linear - Adobe RGB",
"Utility - Linear - Adobe Wide Gamut RGB",
"Utility - Linear - P3-D60",
"Utility - Linear - P3-D65",
"Utility - Linear - P3-DCI",
"Utility - Linear - RIMM ROMM (ProPhoto)",
"Utility - Linear - Rec.2020",
"Utility - Linear - Rec.709",
"Utility - Linear - sRGB",
"Utility - Rec.2020 - Camera",
"Utility - Rec.2020 - Display",
"Utility - Rec.709 - Camera",
"Utility - Rec.709 - Display",
"Utility - XYZ - D60",
"Utility - sRGB - Texture",
"Utility - Raw",
"Utility - Look - ACES 1.0 to 0.1 emulation",
"Utility - Look - ACES 1.0 to 0.2 emulation",
"Utility - Look - ACES 1.0 to 0.7 emulation",
"Role - reference",
"Role - compositing_linear",
"Role - compositing_log",
"Role - rendering",
"Role - scene_linear",
"Role - texture_paint",
"Role - default",
"Role - data",
"Role - matte_paint",
"Role - color_picking",
"Role - color_timing",
"lin_ap0",
"aces",
"acescc",
"acescc_ap1",
"acescct",
"acescct_ap1",
"acesproxy",
"acesproxy_ap1"
"acescg",
"lin_ap1",
"adx10",
"adx16",
"logc3ei160_alexawide",
"logc3ei200_alexawide",
"logc3ei250_alexawide",
"logc3ei320_alexawide",
"logc3ei400_alexawide",
"logc3ei500_alexawide",
"logc3ei640_alexawide",
"logc3ei800_alexawide",
"logc3ei1000_alexawide",
"logc3ei1280_alexawide",
"logc3ei1600_alexawide",
"logc3ei2000_alexawide",
"logc3ei2560_alexawide",
"logc3ei3200_alexawide",
"crv_logc3ei800",
"lin_alexawide",
"canonlog_rec709day",
"canonlog_rec709tung",
"canonlog_dcip3day",
"canonlog_dcip3tung",
"canonlog_cgamutday",
"canonlog_cgamuttung",
"canonlog_rec2020day",
"canonlog_rec2020tung",
"canonlog2_rec2020day",
"canonlog2_rec2020tung",
"canonlog2_cgamutday",
"canonlog2_cgamuttung",
"canonlog3_rec2020day",
"canonlog3_rec2020tung",
"canonlog3_cgamutday",
"canonlog3_cgamuttung",
"crv_canonlog",
"crv_canonlog2",
"crv_canonlog3",
"lin_canonrec709day",
"lin_canonrec709tung",
"lin_canondcip3day",
"lin_canondcip3tung",
"lin_canoncgamutday",
"lin_canoncgamuttung",
"lin_canonrec2020day",
"lin_canonrec2020tung",
"protuneflat_protunegamutexp",
"crv_protuneflat",
"lin_protunegamutexp",
"vlog_vgamut",
"crv_vlog",
"lin_vgamut",
"rlf_dgn",
"rlf_dgn2",
"rlf_rc",
"rlf_rc2",
"rlf_rc3",
"rlf_rc4",
"rl3g10_rwg",
"crv_rlf",
"crv_rl3g10",
"lin_dgn",
"lin_dgn2",
"lin_rc",
"lin_rc2",
"lin_rc3",
"lin_rc4",
"lin_rwg",
"slog1_sgamut",
"slog2_sgamut",
"slog2_sgamutday",
"slog2_sgamuttung",
"slog3_sgamutcine",
"slog3_sgamut3",
"crv_slog1",
"crv_slog2",
"crv_slog3",
"lin_sgamut",
"lin_sgamutday",
"lin_sgamuttung",
"lin_sgamut3cine",
"lin_sgamut3",
"out_dcdmp3gamutclip",
"out_dcdm",
"out_p3d60st20841000nits",
"out_p3d60st20842000nits",
"out_p3d60st20844000nits",
"out_rec2020st20841000nits",
"out_p3d60",
"out_p3dci",
"out_rec2020",
"out_rec709",
"out_rec709d60sim",
"out_srgb",
"out_srgbd60sim",
"crv_lmtshaper",
"crv_log248nitsshaper",
"log248nitsshaper_ap1",
"crv_log21000nitsshaper",
"log21000nitsshaper_ap1",
"crv_log22000nitsshaper",
"log22000nitsshaper_ap1",
"crv_log24000nitsshaper",
"log24000nitsshaper_ap1",
"crv_dolbypq_10000",
"crv_dolbypq48nitsshaper",
"dolbypq48nitsshaper_ap1",
"crv_dolbypq1000nitsshaper",
"dolbypq1000nitsshaper_ap1",
"crv_dolbypq2000nitsshaper",
"dolbypq2000nitsshaper_ap1",
"crv_dolbypq4000nitsshaper",
"dolbypq4000nitsshaper_ap1",
"crv_rec1886",
"crv_rec2020",
"crv_rec709",
"crv_srgb",
"lin_adobergb",
"lin_adobewidegamutrgb",
"lin_p3d60",
"lin_p3d65",
"lin_p3dci",
"lin_prophoto",
"lin_rimm",
"lin_rec2020",
"lin_rec709",
"lin_srgb",
"rec2020_camera",
"rec2020_display",
"rec709_camera",
"rec709_display",
"lin_xyz_d60",
"srgb_texture",
"raw",
"look_aces10to01emulation",
"look_aces10to02emulation",
"look_aces10to07emulation",
"role_reference",
"role_compositing_linear",
"role_compositing_log",
"role_rendering",
"role_scene_linear",
"role_texture_paint",
"role_default",
"role_data",
"role_matte_paint",
"role_color_picking",
"role_color_timing"

Known displays:
	"ACES"* (views:
			"sRGB"*,
			"DCDM",
			"DCDM P3 gamut clip",
			"P3-D60",
			"P3-D60 ST2084 1000 nits",
			"P3-D60 ST2084 2000 nits",
			"P3-D60 ST2084 4000 nits",
			"P3-DCI",
			"Rec.2020",
			"Rec.2020 ST2084 1000 nits",
			"Rec.709",
			"Rec.709 D60 sim.",
			"sRGB D60 sim.",
			"Raw",
			"Log"
		) (* = default)
```

oiiotool을 사용할 준비가 끝났습니다.

## ACES exr to rec709
oiiotool을 가장 많이 사용할 때는 ACES exr 파일을 아티스트가 보기 편한 rec709 컬러스페이스 프리뷰 이미지로 변환하는 일입니다. 변환해 보겠습니다.

테스팅 할 것

```bash
$ oiiotool -i input.exr --colorconvert "ACES - ACEScg" "Output - Rec.709" -o ouput.jpg
```

프리뷰 이미지를 만들 때 --fit 옵션을 사용하면 리사이즈 할 수 있습니다.

```
$ oiiotool -i input.exr --colorconvert "ACES - ACEScg" "Output - Rec.709" --fit 320x240 -o ouput.jpg
```
## Dpx to sRGB
참고 : ADX10은 ACES DPX 10bit 의 약자입니다.

```bash
$ oiiotool -i input.dpx --colorconvert "Input - ADX - ADX10" "Output - sRGB" -o ouput.jpg
```

만약 dpx가 Arri V3 LogC 커브로 인코딩 되어있다면 아래같은 옵션을 사용할 수 있습니다.
```bash
$ oiiotool -i input.dpx --colorconvert "Input - ARRI - Curve - V3 LogC (EI800)" "Output - sRGB" -o ouput.jpg
```

## .exr to .tga
일반적으로 .exr 이미지는 linear 컬러스페이스를 가지며, tga 파일은 sRGB 컬러스페이스를 가집니다.
oiiotool 명령어는 기본적으로 이미지 알파 채널에 대해서 premult를 하지 않으니 알파가 있는 exr 이미지 컨버팅시에는 꼭 `--premult` 옵션을 달아주세요.

```bash
$ oiiotool -i input.exr --colorconvert linear srgb --premult -o output.tga
```

## 컴파일
위에서 필요한 명령어는 간단하게 설치가 끝났습니다.
명령어를 위해서 컴파일 할 필요는 없지만, 다른 프로그램을 컴파일할 때 활용됩니다.

```bash
# yum install clang
```

아래 명령어를 실행하면 일단 빌드가 됩니다.
oiio와 함께 연동이 필요한 라이브러리는 필요시 추가하여 빌드합니다.
```bash
$ cd ~/app
$ git clone https://github.com/OpenImageIO/oiio OpenImageIO_src
$ mkdir OpenImageIO_build
$ mkdir OpenImageIO
$ cd OpenImageIO_build
$ scl enable devtoolset-6 bash
$ ~/app/cmake-3.13.2/bin/cmake ../OpenImageIO_src -DILMBASE_INCLUDE_PATH=$HOME/app/IlmBase/include -DOPENEXR_INCLUDE_PATH=$HOME/app/OpenEXR/include
-DCMAKE_INSTALL_DIR=$HOME/app/OpenImageIO
make
make install
```


필요한 라이브러리
```
CMake Warning (dev) at /home/woong/app/cmake-3.13.2/share/cmake-3.13/Modules/FindOpenGL.cmake:270 (message):
  Policy CMP0072 is not set: FindOpenGL prefers GLVND by default when
  available.  Run "cmake --help-policy CMP0072" for policy details.  Use the
  cmake_policy command to set the policy and suppress this warning.

  FindOpenGL found both a legacy GL library:

    OPENGL_gl_LIBRARY: /usr/lib64/libGL.so

  and GLVND libraries for OpenGL and GLX:

    OPENGL_opengl_LIBRARY: /usr/lib64/libOpenGL.so
    OPENGL_glx_LIBRARY: /usr/lib64/libGLX.so

  OpenGL_GL_PREFERENCE has not been set to "GLVND" or "LEGACY", so for
  compatibility with CMake 3.10 and below the legacy GL library will be used.
Call Stack (most recent call first):
  src/cmake/externalpackages.cmake:131 (find_package)
  CMakeLists.txt:130 (include)
This warning is for project developers.  Use -Wno-dev to suppress it.

-- OCIO not found. Specify OCIO_PATH to locate it
-- Skipping OpenColorIO support
-- FFMPEG not found
-- Field3d will not be used
-- Intel TBB not found, TBB_ROOT_DIR=''
-- OpenVDB will not be used, could not find Intel TBB
-- LibRaw not found!
-- WebP library not found
-- OpenCV library not found
-- DCMTK_INCLUDE_DIR = DCMTK_INCLUDE_DIR-NOTFOUND
-- DCMTK not found. Specify DCMTK_PATH to locate it
-- Downloading local Tessil/robin-map
-- robin-map include dir: /home/woong/app/OpenImageIO_src/ext/robin-map
CMake Warning at src/dicom.imageio/CMakeLists.txt:7 (message):
  DICOM plugin will not be built, no DCMTK


-- FFmpeg not found: ffmpeg plugin will not be built
CMake Warning at src/gif.imageio/CMakeLists.txt:7 (message):
  GIF plugin will not be built


CMake Warning at src/jpeg2000.imageio/CMakeLists.txt:16 (message):
  Jpeg-2000 plugin will not be built


CMake Warning at src/raw.imageio/CMakeLists.txt:7 (message):
  Raw plugin will not be built


-- WebP plugin will not be built
-- pybind11 include dir: /home/woong/app/OpenImageIO_src/ext/pybind11/include
-- Python version 2.7.5
-- Could not Find Nuke. Skipping build of Nuke plugins.
-- 

Did not find /home/woong/app/OpenImageIO_src/../oiio-images
--   -> Will not run tests gpsread;oiiotool;oiiotool-attribs;oiiotool-readerror;oiiotool-xform;oiiotool-fixnan;maketx;oiiotool-maketx;misnamed-file;dpx;ico;iff;png;psd;rla;sgi;zfile;texture-interp-bicubic;texture-blurtube;texture-crop;texture-cropover;texture-derivs;texture-fill;texture-filtersize;texture-flipt;texture-gettexels;texture-gray;texture-mip-nomip;texture-mip-trilinear;texture-overscan;texture-pointsample;texture-uint8;texture-width0blur;texture-fat;texture-skinny;texture-wrapfill;texture-missing;texture-res;texture-udim;texture-udim2
--   -> You can find it at 

-- 

Did not find /home/woong/app/OpenImageIO_src/../openexr-images
--   -> Will not run tests oiiotool-deep
--   -> You can find it at 

-- 

Did not find /home/woong/app/OpenImageIO_src/../oiio-images
--   -> Will not run tests python-typedesc;python-imagespec;python-roi;python-deep;python-imageinput;python-imageoutput;python-imagebuf;python-imagebufalgo
--   -> You can find it at 

-- 

Did not find /home/woong/app/OpenImageIO_src/../bmpsuite
--   -> Will not run tests bmp
--   -> You can find it at http://entropymine.com/jason/bmpsuite/bmpsuite.zip

-- 

Did not find /home/woong/app/OpenImageIO_src/../libtiffpic
--   -> Will not run tests tiff-suite;tiff-depths;tiff-misc
--   -> You can find it at http://www.simplesystems.org/libtiff/images.html

-- 

Did not find /home/woong/app/OpenImageIO_src/../openexr-images
--   -> Will not run tests openexr-suite;openexr-multires;openexr-chroma;openexr-v2;perchannel
--   -> You can find it at http://www.openexr.com/downloads.html

-- 

Did not find /home/woong/app/OpenImageIO_src/../oiio-images
--   -> Will not run tests gif
--   -> You can find it at Recent checkout of oiio-images

-- 

Did not find /home/woong/app/OpenImageIO_src/../j2kp4files_v1_5
--   -> Will not run tests jpeg2000
--   -> You can find it at http://www.itu.int/net/ITU-T/sigdb/speimage/ImageForm-s.aspx?val=10100803

-- 

Did not find /home/woong/app/OpenImageIO_src/../oiio-images/pnm
--   -> Will not run tests pnm
--   -> You can find it at Recent checkout of oiio-images

-- 

Did not find /home/woong/app/OpenImageIO_src/../oiio-images/raw
--   -> Will not run tests raw
--   -> You can find it at Recent checkout of oiio-images

-- 

Did not find /home/woong/app/OpenImageIO_src/../TGAUTILS
--   -> Will not run tests targa-tgautils
--   -> You can find it at http://tgautils.inequation.org/

-- 

Did not find /home/woong/app/OpenImageIO_src/../fits-images
--   -> Will not run tests fits
--   -> You can find it at http://www.cv.nrao.edu/fits/data/tests/

-- 

Did not find /home/woong/app/OpenImageIO_src/../webp-images
--   -> Will not run tests webp
--   -> You can find it at http://code.google.com/speed/webp/gallery.html

-- Configuring done
CMake Warning at src/iv/CMakeLists.txt:12 (add_executable):
  Cannot generate a safe runtime search path for target iv because files in
  some directories may conflict with libraries in implicit directories:

    runtime library [libQt5OpenGL.so.5] in /usr/lib64 may be hidden by files in:
      /usr/local/lib
    runtime library [libQt5Widgets.so.5] in /usr/lib64 may be hidden by files in:
      /usr/local/lib
    runtime library [libQt5Gui.so.5] in /usr/lib64 may be hidden by files in:
      /usr/local/lib
    runtime library [libQt5Core.so.5] in /usr/lib64 may be hidden by files in:
      /usr/local/lib

  Some of these libraries may not be found correctly.
```
## Reference
- https://github.com/OpenImageIO/oiio/blob/master/src/doc/openimageio.pdf
- [webp 란?](https://ko.wikipedia.org/wiki/WebP) : jpeg를 대체하기 위해 구글에서 개발된 포멧
