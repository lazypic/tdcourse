# ACES / OpenColorIO
ACES는 Academy Color Encoding Specification의 약자입니다.
OpenColorIO는 ACES 표준을 따르는 컬러메니징 솔루션입니다.

소니이미지웍스에서 개발되었습니다.

## 지원하는 프로그램
- Houdini
- Katana
- Mari
- Nuke
- Krita
- Blender
- Gaffer
- Vray
- Renderman
- Natron
- [언리얼](https://docs.unrealengine.com/en-us/Engine/Rendering/PostProcessEffects/ColorGrading)

## OpenColorIO-Configs 셋팅하기
OpenColorIO-Configs는 OpenColorIO의 컬러 설정파일입니다.

기본적으로 뉴크에는 OCIO가 탑재되어있습니다. 만약 내부 버전보다 더 높은 버전을 사용하고 싶다면 아래 설정을 따라해주세요.

```bash
cd ~/app
git clone https://github.com/imageworks/OpenColorIO-Configs
```

뉴크에 기본 탑재된 OCIO가 아닌 위 Configs 파일을 이용하고 싶다면 환경변수에 OCIO경로를 지정하면 뉴크가 자동으로 인식하여 뉴크 실행시 OpenColorIO-Configs를 로딩합니다.

환경변수 파일에 아래 내용을 추가합니다.
```
export OCIO=$HOME/app/OpenColorIO-Configs/aces_1.0.3/config.ocio
```

## OpenColorIO 컴파일
OpenColorIO를 컴파일하면 각종 라이브러리, 명령어를 추가로 사용할 수 있습니다.

- 소스코드 : https://github.com/imageworks/OpenColorIO


필요한 라이브러리
```
# yum install glew-devel
```

```
cd ~/app
git clone https://github.com/imageworks/OpenColorIO OpenColorIO_src
mkdir OpenColorIO_build
cd OpenColorIO_build
scl enable devtoolset-6 bash
/opt/cmake3.13/bin/cmake ../OpenColorIO_src -DCMAKE_INSTALL_PREFIX=$HOME/app/OpenColorIO -DGLEW_INCLUDE_DIR=/usr/include -DGLEW_LIBRARY=/usr/lib64 -DOCIO_BUILD_GPU_TESTS=OFF
-DOIIO_LIBRARIES= -DOIIO_INCLUDE_DIR= -DOIIO_LIBRARY_DIR=
make
make install
```

## 명령어
명령어를 실행하기 위해서는 libOpenColorIO.so.2.0 파일이 필요합니다.
```bash
$ export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$HOME/app/OpenColorIO/lib
$ export OCIO=$HOME/app/OpenColorIO-Configs/aces_1.0.3/config.ocio
```

## ociobakelut
ocio를 이용해서 lut를 생성합니다.

```bash
$ ociobakelut --inputspace "ACES - ACEScg" --outputspace "Output - Rec.709" --format flame flame_acescg_to_rec709.3dl
```

#### 지원하는 포멧
- flame (.3dl)
- lustre (.3dl)
- cinespace (.csp)
- houdini (.lut)
- iridas_itx (.itx)
- iridas_cube (.cube)
- truelight (.cub)
- resolve_cube (.cube)
- icc (.icc)

#### ociocheck
config.ocio 정보가 문제없는지 체크합니다.

사용법
```bash
$ ociocheck
```

Output
```
OpenColorIO Library Version: 2.0.0dev
OpenColorIO Library VersionHex: 33554432
Loading $OCIO /home/woong/app/OpenColorIO-Configs/aces_1.0.3/config.ocio

** General **
Search Path: luts
Working Dir: /home/woong/app/OpenColorIO-Configs/aces_1.0.3

Default Display: ACES
Default View: sRGB

** Roles **
ACES - ACES2065-1 (default)
ACES - ACEScg (scene_linear)
Utility - Raw (data)
Utility - Raw (reference)
Input - ADX - ADX10 (compositing_log)
ACES - ACEScc (color_timing)
Output - Rec.709 (color_picking)
ACES - ACEScc (texture_paint)
Utility - sRGB - Texture (matte_paint)
ACES - ACEScg (compositing_linear: user)
ACES - ACEScg (rendering: user)

** ColorSpaces **
ACES - ACES2065-1
ACES - ACEScc
ACES - ACEScct
ACES - ACESproxy
ACES - ACEScg
Input - ADX - ADX10
...
Tests complete.
```

맨 마지막에 Tests complete. 문구가 뜨면 정상입니다.

## OCIO를 지원하는 툴
- Renderman
- Vray
- Arnold
- Kantana
- Nuke
- Blender
- Krita
- Silhouette
- Hiero
- Rv
- Gaffer
- Natron

## ACES 2065-1, ACEScg, ACEScc
일반적으로 CG 작업에는 ACEScg를 사용합니다.
ACES 프로젝트중 데이터를 ACES 2065-1로 보내달라고 하는 경우가 있습니다.

- ACES 2065-1 : 표준 ACES 컬러스페이스 입니다.
- ACEScg : 일반적으로 Visual Effects 프로그램에서 컬러를 인코딩하기 위해서 사용하는 ACES 컬러스페이스입니다.
- ACEScc : ACES의 로그 컬러스페이스입니다.

#### Reference
- https://community.foundry.com/discuss/topic/137176/about-the-aces-vfx-pulls-aces-2065-1-or-acescg
- https://www.slideshare.net/hpduiker/acescg-a-common-color-encoding-for-visual-effects-applications

## OCIO Core Library
OCIO Core Library는 OpenImageIO 같은 툴을 컴파일할 때 간혹 사용한다. 아래 링크에서 Core Library를 다운로드 받을 수 있다.

http://opencolorio.org/downloads.html#downloads

## Reference
- ociobakelut : http://opencolorio.org/CompatibleSoftware.html
- http://opencolorio.org/userguide/tool_overview.html