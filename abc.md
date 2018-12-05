# Alembic
Alembic은 3D 데이터를 교환하기 위해서 만들어진 Framework입니다.
소니이미지웍스와 ILM이 같이 개발하고 있습니다.

아래 상황에서 자주 사용합니다. 발췌 : http://www.alembic.io

- 애니메이션 데이터를 베이크하여 라이팅, 렌더링 할 때
- 애니메이션된 크리쳐 데이터에서 옷이나 피부를 시뮬레이션 할 때
- 옷, 피부 데이터를 저장하여 라이팅, 렌더링 할 때
- 애니메이션된 물체를 물리엔진으로 넘길 때
- 물리엔진에서 연산된 데이터를 라이팅, 렌더링으로 넘길 때

마야같은 툴에서 이미 abc 파일을 export 할 수 있습니다.
또한 우리가 배울 nuke에서는 abc파일을 import 할 수 있습니다.

## abc를 지원하는 프로그램
- Maya
- Katana
- Houdini
- Nuke
- 3dsmax
- Blender
- [Unreal](https://docs.unrealengine.com/en-us/Engine/Content/AlembicImporter)

## Alembic 컴파일하기
소스코드 : https://github.com/alembic/alembic

abc는 Ogawa, Hdf5 두가지 포멧을 지원합니다.
교육의 편의성을 위해서 소스코드를 이용하여 Ogawa(기본값) 형식만 지원하도록 컴파일 하겠습니다. Ogawa 파일은 HDF5 보다 용량이 작고 더 빠르게 로드됩니다. HDF5는 예전에 abc에서 사용하던 방식입니다. IlmBase 라이브러리는 컴파일 중간에 사용되며 OpenEXR 컴파일 할 때 이미 생성한 데이터를 사용할 예정입니다.

```bash
$ cd ~/app
$ git clone https://github.com/alembic/alembic alembic_src
$ mkdir alembic_build
$ mkdir alembic
$ cd alembic_build
$ scl enable devtoolset-6 bash
# yum install devtoolset-6-libatomic-devel // 중간에 libatomic 에러가나 나면 설치해줍니다.
$ cmake ../alembic_src -DILMBASE_ROOT=$HOME/app/IlmBase -DALEMBIC_SHARED_LIBS=OFF -DUSE_HDF5=OFF -DALEMBIC_LIB_USES_TR1=ON -DCMAKE_INSTALL_PREFIX=$HOME/app/alembic
$ make -j2
$ make install
$ make help
```

컴파일이 되면 아래 명령어를 사용할 수 있게 됩니다.

- abcdiff

    2개의 abc 파일을 입력해서 다른 부분만 abc파일로 출력됩니다.
    다른 부분이 없다면 `No differences detected` 메시지가 출력됩니다.
    ```
    $ abcdiff input1.abc input2.abc output.abc
    ```

- abcecho

    .abc파일의 디테일한 정보를 볼 수 있습니다.
    ```
    $ abcecho box.abc
    ```
    ```
    AbcEcho for Alembic 1.7.10 (built Dec  5 2018 17:30:01)
    file written by: Blender
    using Alembic : Alembic 1.7.8 (built Sep 10 2018 16:59:10)
    written on : Wed Dec  5 19:56:39 2018
    user description : untitled

    ScalarProperty name=.childBnds;interpretation=box;datatype=float64_t[6];arraysize=6;numsamps=250
    Object name=/Cube
    CompoundProperty name=.xform;schema=AbcGeom_Xform_v3
    ScalarProperty name=.inherits;interpretation=;datatype=bool_t;arraysize=1;numsamps=250
    ScalarProperty name=.ops;interpretation=;datatype=uint8_t;arraysize=1;numsamps=250
    ScalarProperty name=.vals;interpretation=;datatype=float64_t[16];arraysize=16;numsamps=250
    ScalarProperty name=visible;interpretation=;datatype=int8_t;arraysize=1;numsamps=250
    Object name=/Cube/CubeShape
    CompoundProperty name=.geom;schema=AbcGeom_PolyMesh_v1
    ScalarProperty name=.selfBnds;interpretation=box;datatype=float64_t[6];arraysize=6;numsamps=1
    ArrayProperty name=P;interpretation=point;datatype=float32_t[3];arraysize=8;numsamps=1
    ArrayProperty name=.faceIndices;interpretation=;datatype=int32_t;arraysize=24;numsamps=1
    ArrayProperty name=.faceCounts;interpretation=;datatype=int32_t;arraysize=6;numsamps=1
    CompoundProperty name=.userProperties;schema=
    ScalarProperty name=meshtype;interpretation=;datatype=bool_t;arraysize=1;numsamps=1
    CompoundProperty name=.arbGeomParams;schema=
    CompoundProperty name=uv;schema=
    ArrayProperty name=.vals;interpretation=vector;datatype=float32_t[2];arraysize=14;numsamps=1
    ArrayProperty name=.indices;interpretation=;datatype=uint32_t;arraysize=24;numsamps=1
    ArrayProperty name=N;interpretation=normal;datatype=float32_t[3];arraysize=8;numsamps=1
    ```

- abcechobounds

    .abc 파일 내부 바운딩 박스의 사이즈 크기를 반환하는 명령어 입니다.
    ```
    $ abcechobounds box.abc
    ```

    Output:
    ```
    /Cube/CubeShape (-1 -1 -1) (1 1 1)
    / (-1 -1 -1) (1 1 1)
    ```

- abcls

    .abc 파일 내부에 있는 오브젝트 이름을 반환합니다.
    ```
    $ abcls box.abc
    ```

    Output:
    ```
    Cube
    ```

- abcstitcher
    
    각 프레임마다 연산된 .abc 파일을 묶어서 하나의 .abc파일로 만들어줍니다.
    프레임영역이 겹치면 `ERROR: overlapping frame range between` 에러가 발생합니다.
    ```
    $ abcstitcher output.abc input.0001.abc input.0002.abc input.0003.abc ...
    ```
- abctree

    .abc 파일의 구조를 Tree 형태로 그려주는 명령어 입니다.

    ```
    $ abctree box.abc
    ```

    Output:
    ```
    ABC
        --Cube
            --CubeShape
    ```



## abc뷰어
https://github.com/alembic/abcview