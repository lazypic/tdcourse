# OpenVDB

구름처럼 넓게 퍼져있는 볼륨 형태의 데이터를 저장할 때 사용합니다.
계층 구조를 이용하여 효율적으로 저장, 조작하기 위해서 개발된 C++ 라이브러리 입니다.
원래 드림웍스에서 개발되었지만 지금은 [Academy Software Foundation(ASWF)](https://www.aswf.io)에 의해서 관리되고 있습니다.

라이센스 : Mozilla Public License Version 2.0

> 참고 : .vdb 파일은 gaffer에서 미리보기 할 수 있습니다.

지원하는 소프트웨어

- Houdini
- [Renderman](prman.md)
- Arnold
- Realflow
- Clarisse
- Guerilla Render
- Maxwell Render
- Modo
- Vray
- RedShift
- Octane Render
- 3Delight
- VFX Reference Platform
- [Gaffer](gaffer.md)

## 컴파일(진행중)

Youtube 영상을 1차로 따라해보고 기록하기.

소스코드 : https://github.com/AcademySoftwareFoundation/openvdb.git

컴파일을 마치면 아래 명령어를 사용할 수 있습니다.

- openvdb_lod
- openvdb_print
- openvdb_render
- openvdb_view

blosc 설치 : [blosc](http://www.blosc.org)는 바이너리 데이터를 나누고 섞는 무손실 압축 라이브러리 입니다. openVDB에 사용됩니다.

```bash
$ cd ~/app
$ git clone https://github.com/Blosc/c-blosc c-blosc_src
$ mkdir c-blosc_build
$ mkdir c-blosc
$ cd c-blosc_build
$ ~/app/cmake-3.13.2/bin/cmake ../c-blosc_src -DCMAKE_INSTALL_PREFIX=$HOME/app/c-blosc
$ make
$ make install
```

```bash
$ cd ~/app
$ git clone https://github.com/AcademySoftwareFoundation/openvdb.git openvdb_src
$ mkdir openvdb_build
$ mkdir openvdb
$ cd openvdb_build
$ scl enable devtoolset-6 bash
$ ~/app/cmake-3.13.2/bin/cmake ../openvdb_src -DBLOSC_LOCATION=$HOME/app/c-blosc -DCMAKE_INSTALL_PREFIX=$HOME/app/openvdb -DTBB_LOCATION=$HOME/app/tbb
```

## 샘플파일 다운로드

http://www.openvdb.org/download

## Reference

- 컴파일 유투브영상 : https://www.youtube.com/watch?v=aQFzVv_2TTg
- 관련데이터 : http://pointclouds.org