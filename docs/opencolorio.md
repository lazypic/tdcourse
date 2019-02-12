# ACES / OpenColorIO
ACES는 Academy Color Encoding Specification의 약자입니다.
OpenColorIO는 ACES 표준을 따르는 컬러메니징 솔루션입니다.

소니픽쳐스 이미지웍스에서 개발되었습니다.

## 지원하는 프로그램
- Houdini
- Katana
- Mari
- Nuke
- Krita
- Blender
- Gaffer
- Vray
- Arnold
- Renderman
- Natron
- Maya
- Max
- Davinci Resolve
- Photoshop(macOS)
- Silhouette
- Hiero
- Rv
- [Unreal](https://docs.unrealengine.com/en-us/Engine/Rendering/PostProcessEffects/ColorGrading)

## 설치
기본적으로 낮은버전의 OpenColorIO는 아래처럼 설치 가능합니다.

```
# yum install OpenColorIO
```

## OpenColorIO-Configs 셋팅하기
OpenColorIO-Configs는 OpenColorIO의 컬러 설정파일입니다.

기본적으로 뉴크에는 OCIO가 탑재되어있습니다.
뉴크 내부 버전보다 더 높은 버전의 OCIO를 사용하고 싶다면 아래 설정을 따라해주세요.

```bash
$ cd ~/app
$ git clone https://github.com/imageworks/OpenColorIO-Configs
```

뉴크에 기본 탑재된 OCIO가 아닌 위 Configs 파일을 이용하고 싶다면 환경변수에 OCIO경로를 지정하면 뉴크가 자동으로 인식하여 뉴크 실행시 OpenColorIO-Configs를 로딩합니다.

~/centos/env/init.bash 파일에 아래 내용을 추가합니다.
```
export OCIO=$HOME/app/OpenColorIO-Configs/aces_1.0.3/config.ocio
```

## OpenColorIO 컴파일(진행중)
OpenColorIO를 컴파일하면 각종 라이브러리, 명령어를 추가로 사용할 수 있습니다.

- 소스코드 : https://github.com/imageworks/OpenColorIO


필요한 라이브러리
```
# yum install glew-devel
```

```bash
$ scl enable devtoolset-6 bash
$ cd ~/app
$ git clone https://github.com/imageworks/OpenColorIO OpenColorIO_src
$ cd OpenColorIO_src
$ git tag
$ git checkout v1.0.9
$ cd ..
$ mkdir OpenColorIO_build
$ cd OpenColorIO_build
$ ~/app/cmake-3.13.3/bin/cmake ../OpenColorIO_src -DCMAKE_INSTALL_PREFIX=$HOME/app/OpenColorIO
$ make
$ make install
```

v1.1.0으로 컴파일하지 않는 이유.
- 이슈 : https://github.com/imageworks/OpenColorIO/issues/617

## 명령어
OCIO 명령어를 실행하기 위해서는 libOpenColorIO.so.2.0 파일이 필요합니다.
~/centos/env/init.bash에 설정해줍니다.

설정하지 않으면 아래형태의 에러가 발생합니다.

```
./ociobakelut: symbol lookup error: ./ociobakelut: undefined symbol: _ZdlPvm
```

```bash
$ export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$HOME/app/OpenColorIO/lib
$ export OCIO=$HOME/app/OpenColorIO-Configs/aces_1.0.3/config.ocio
```

## ociobakelut
ocio를 이용해서 lut를 생성합니다.

```bash
$ ociobakelut --inputspace "ACES - ACEScg" --outputspace "Output - Rec.709" --format flame flame_acescg_to_rec709.3dl
```

#### ociobakelut명령어가 지원하는 포멧
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
계속 출력됩니다.
...
Tests complete.
```

맨 마지막에 Tests complete. 문구가 뜨면 정상입니다.


## ACES 2065-1, ACEScg, ACEScc
일반적으로 CG 작업에는 ACEScg를 사용합니다.
ACES 프로젝트중 데이터를 ACES 2065-1로 보내달라고 하는 경우가 있습니다.

- ACES 2065-1 : 표준 ACES 컬러스페이스 입니다.
- ACEScg : 일반적으로 Visual Effects 프로그램에서 컬러를 인코딩하기 위해서 사용하는 ACES 컬러스페이스입니다.
- ACEScc : ACES에서 사용하는 Log 컬러스페이스입니다.

#### Reference
- https://community.foundry.com/discuss/topic/137176/about-the-aces-vfx-pulls-aces-2065-1-or-acescg
- https://www.slideshare.net/hpduiker/acescg-a-common-color-encoding-for-visual-effects-applications

## OCIO Core Library
OCIO Core Library는 OpenImageIO 같은 툴을 컴파일할 때 간혹 사용됩니다.
아래 링크에서 Core Library를 다운로드 받을 수 있습니다.

http://opencolorio.org/downloads.html#downloads

## 실 습
- OpenColorIO-Configs 설치를 자동화 합니다.
- OCIO 컴파일 스크립트를 자동화합니다.
- OCIO 환경변수를 설정하고 뉴크를 실행합니다. 다시 OCIO 환경변수를 제거하고 뉴크를 실행합니다. 제거하는 방법은 아래와 같습니다.
```
$ unset OCIO
```
- bin를 환경변수에 추가하기
```
export PATH=$HOME/app/OpenColorIO/bin:$PATH
```

## Reference
- ociobakelut : http://opencolorio.org/CompatibleSoftware.html
- http://opencolorio.org/userguide/tool_overview.html
