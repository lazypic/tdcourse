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

소스코드를 이용하여 Ogawa(기본값) 형식만 지원하도록 컴파일 하겠습니다. Ogawa 파일은 HDF5 보다 용량이 작고 더 빠르게 로드됩니다. HDF5는 예전에 abc에서 사용하던 방식입니다. IlmBase 라이브러리는 OpenEXR 컴파일 할 때 이미 진행했습니다.

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

- abcdiff : 
- abcecho : 
- abcechobounds : 
- abcls : 
- abcstitcher : 
- abctree : 


## abc뷰어
https://github.com/alembic/abcview