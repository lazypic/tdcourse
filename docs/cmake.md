# Cmake
Cross Platform을 위한 빌드를 지원하는 툴입니다.
cmake는 make 파일을 만들 때 사용하는 유틸리티입니다.
cmake는 스스로 make 하지 않고, 각각의 OS에 맞는 make 파일을 만들기 위해서 사용됩니다.
CentOS7.9에 설치되는 기본 cmake는 버전이 낮아서 앞으로 우리가 사용하게 될 툴들을 빌드할 때 자주 버전이 낮다고 경고가 뜨게됩니다.
앞으로 강의를 진행하기 전에 미리 높은 버전의 cmake를 같이 설치해봅시다.

> 참고 : make는 프로그램 그룹을 유지할 때 사용하는 툴입니다.
소스코드(입력 파일)가 바뀌면 자동적으로 결과 파일이 바뀌기를 원할 때(예) 소스코드가 바뀌면 다시 컴파일 해야할 때) 순차적으로 프로그램이 수행이 되기를 바랄 때 사용합니다.

## 높은 버전의 GCC 설치하기 (gcc9 - vfx reference platform 2021)
최신 cmake를 컴파일 하기 위해서 최신 gcc가 필요합니다.
설치하겠습니다.

참고 : [devtoolset-9을 설치하면 같이 설치되는 프로그램 리스트](https://access.redhat.com/documentation/en-us/red_hat_developer_toolset/9/html-single/user_guide/index)

```
# yum install centos-release-scl-rh
# yum --enablerepo=centos-sclo-rh-testing install devtoolset-9
```

## cmake 다운로드 및 설치
- https://cmake.org/download/ 에서 리눅스용 cmake를 다운로드 받습니다.

```
$ cd /tmp
$ wget https://github.com/Kitware/CMake/releases/download/v3.13.3/cmake-3.13.3.tar.gz
$ tar -zxvf cmake-3.13.3.tar.gz -C ~/app
$ cd ~/app
$ mv ~/app/cmake-3.13.3 ~/app/cmake-3.13.3_src
$ mkdir cmake-3.13.3
$ cd ~/app/cmake-3.13.3_src
$ ./configure --prefix=$HOME/app/cmake-3.13.3
$ make
$ make install
```

## 실습
- cmake를 설치하는 스크립트를 작성하고 Github에 올립니다.
- cmake 라고 터미널에 실행했을 때 높은 버전의 cmake가 작동되도록 alias를 설정합니다.
