# OpenVDB
최초 드림웍스에서 개발된 C++ 라이브러리 입니다.
계층데이터를 구성하거나, 볼륨데이터를 적은 용량으로 효율적 저장, 조작하기 위해서 개발되었습니다.
현재 이 프로젝트는 [Academy Software Foundation(ASWF)](https://www.aswf.io)에 의해서 관리되고 있습니다.

라이센스 : Mozilla Public License Version 2.0

지원하는 소프트웨어
- Houdini
- Renderman
- Arnold
- Realflow
- Clarisse
- Guerilla Render
- Maxwell Render
- Modo
- Vray
- Octane Render
- 3Delight
- VFX Reference Platform

## 컴파일

소스코드 : https://github.com/AcademySoftwareFoundation/openvdb.git

컴파일을 마치면 아래 명령어를 사용할 수 있습니다.
- openvdb_lod
- openvdb_print
- openvdb_render
- openvdb_view

blosc 설치 : [blosc](http://www.blosc.org)는 바이너리 데이터를 나누고 섞는 무손실 압축 라이브러리 입니다. openVDB에 사용됩니다.
```
$ cd ~/app
$ git clone https://github.com/Blosc/c-blosc c-blosc_src
$ mkdir c-blosc_build
$ mkdir c-blosc
$ cd c-blosc_build
$ ~/app/cmake-3.13.2/bin/cmake ../c-blosc_src -DCMAKE_INSTALL_PREFIX=$HOME/app/c-blosc
$ make
$ make install
```

```
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