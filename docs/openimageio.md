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

## 명령어
OpenImageIO, OpenImageIO Util 명령어를 알아보겠습니다.

### iinfo
이미지의 정보를 분석하는 툴입니다.

```bash
$ iinfo test.exr 
test.exr : 2880 x 1620, 3 channel, half openexr
```

### iconvert
이미지를 컨버팅할 때 사용합니다.

```bash
$ iconvert --inplace --caption testimage test.exr
```

이미지에 키워드 추가하기
```bash
$ iconvert --inplace --keyword woong test.exr
```

exr이미지에 어트리뷰트 추가하기
```bash
$ iconvert --inplace --attrib project circle --attrib shot FOO_0010 test.exr
```
### idiff
이미지를 비교하는 명령어

PASS 문자가 출력되면 같은 이미지 입니다.
```bash
$ idiff image1.exr image2.exr 
Comparing "image1.exr" and "image2.exr"
PASS
```

결과가 다르면 분석값을 출력하고 FAILURE을 최종 출력합니다.
```
$ idiff image1.exr image2.exr
Comparing "image1.exr" and "image2.exr"
  Mean error = 0.327311
  RMS error = 0.508405
  Peak SNR = 28.74
  Max error  = 13.0548 @ (843, 275, B)
  4665600 pixels (100%) over 1e-06
  4665600 pixels (100%) over 1e-06
FAILURE
```
### igrep
이미지 메타데이터를 검색할 때 사용합니다.

만약 이미지 내부에 `A004R23J` 문자가 존재하는지 검사할 때

```bash
$ igrep A004R23J test.exr
```


### oiiotool
OpenImageIO를 설치하면 사용할 수 있는 이미지 프로세싱 툴입니다.
가장 많이 사용하게 될 명령어 입니다.

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
# yum install webp-devel
# yum install LibRaw-devel
# yum install opencv-devel
```

OpenColorIO Core 가 필요합니다. app에 설치해주세요.
```
cd ~/app
wget http://github.com/imageworks/OpenColorIO/tarball/v1.0.9
tar -zxvf v1.0.9
```

아래 명령어를 실행하면 일단 빌드가 됩니다.
oiio와 함께 연동이 필요한 라이브러리는 필요시 추가하여 빌드합니다.
```bash
$ cd ~/app
$ git clone https://github.com/OpenImageIO/oiio OpenImageIO_src
$ mkdir OpenImageIO
$ mkdir OpenImageIO_build
$ cd OpenImageIO_build
$ scl enable devtoolset-6 bash
$ ~/app/cmake-3.13.2/bin/cmake -DSTOP_ON_WARNING=0 ../OpenImageIO_src -DOPENEXR_INCLUDE_DIR=$HOME/app/openexr/include -DOPENEXR_LIB_DIR=$HOME/app/openexr/lib -DILMBASE_INCLUDE_DIR=$HOME/app/IlmBase/include -DILMBASE_LIB_DIR=$HOME/app/IlmBase/lib -DOCIO_PATH=$HOME/app/OpenColorIO -DCMAKE_INSTALL_PREFIX=$HOME/app/OpenImageIO
$ make
$ make install
```

에러내용 : https://github.com/OpenImageIO/oiio/issues/1406
```
[ 74%] Linking CXX executable simd_test
/opt/rh/devtoolset-6/root/usr/libexec/gcc/x86_64-redhat-linux/6.3.1/ld: warning: libHalf.so.24, needed by /home/woong/app/openexr/lib/libIlmImf.so, may conflict with libHalf.so.6
/opt/rh/devtoolset-6/root/usr/libexec/gcc/x86_64-redhat-linux/6.3.1/ld: warning: libHalf.so.24, needed by /home/woong/app/openexr/lib/libIlmImf.so, may conflict with libHalf.so.6
/opt/rh/devtoolset-6/root/usr/libexec/gcc/x86_64-redhat-linux/6.3.1/ld: CMakeFiles/simd_test.dir/simd_test.cpp.o: undefined reference to symbol '_ZTIN7Iex_2_37BaseExcE'
//home/woong/app/IlmBase/lib/libIex-2_3.so.24: error adding symbols: DSO missing from command line
collect2: error: ld returned 1 exit status
src/libutil/CMakeFiles/simd_test.dir/build.make:130: 'src/libutil/simd_test' \ud0c0\uac9f\uc5d0 \ub300\ud55c \uba85\ub839\uc774 \uc2e4\ud328\ud588\uc2b5\ub2c8\ub2e4
make[2]: *** [src/libutil/simd_test] \uc624\ub958 1
CMakeFiles/Makefile2:1346: 'src/libutil/CMakeFiles/simd_test.dir/all' \ud0c0\uac9f\uc5d0 \ub300\ud55c \uba85\ub839\uc774 \uc2e4\ud328\ud588\uc2b5\ub2c8\ub2e4
make[1]: *** [src/libutil/CMakeFiles/simd_test.dir/all] \uc624\ub958 2
Makefile:162: 'all' \ud0c0\uac9f\uc5d0 \ub300\ud55c \uba85\ub839\uc774 \uc2e4\ud328\ud588\uc2b5\ub2c8\ub2e4
make: *** [all] \uc624\ub958 2
[woong@localhost OpenImageIO_build]$ ~/app/cmake-3.13.2/bin/cmake -DSTOP_ON_WARNING=0 ../OpenImageIO_src -DOPENEXR_INCLUDE_DIR=$HOME/app/openexr/include -DOPENEXR_LIB_DIR=$HOME/app/openexr/lib -DILMBASE_INCLUDE_DIR=$HOME/app/IlmBase/include -DILMBASE_LIB_DIR=$HOME/app/IlmBase/lib -DOCIO_PATH=$HOME/app/OpenColorIO -DCMAKE_INSTALL_PREFIX=$HOME/app/OpenImageIO

```

## Reference
- https://github.com/OpenImageIO/oiio/blob/master/src/doc/openimageio.pdf
- [webp 란?](https://ko.wikipedia.org/wiki/WebP) : jpeg를 대체하기 위해 구글에서 개발된 포멧
