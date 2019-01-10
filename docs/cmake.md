# Cmake
Cross Platform을 위한 빌드 지원 툴입니다.
스스로 make 하지 않고, 각 OS에 맞는 make 파일을 만들기 위해서 사용합니다. CentOS7.6의 기본 cmake 는 버전이 낮아서 앞으로 우리가 사용하게 될 툴을 빌드할 때 버전이 낮다고 자주 경고가 뜹니다. 미리 cmake를 설치해봅시다.

> 참고 : make는 프로그램 그룹을 유지할 때 사용하는 툴입니다.
일반적으로 소스코드(입력 파일)가 바뀌면 자동적으로 결과 파일이 바뀌기를 원할 때(소스코드가 바뀌면 다시 컴파일 해야할 때)
순차적으로 프로그램이 수행이 되기를 바랄 때 사용합니다.

## 설치
https://cmake.org/download/ 에서 리눅스용 cmake를 다운로드 받습니다.

```
$ cd ~/Downloads
$ tar -zxvf cmake-3.13.2.tar.gz -C ~/app
$ cd ~/app
$ mv ~/app/cmake-3.13.2 ~/app/cmake-3.13.2_src
$ mkdir cmake-3.13.2
$ cd ~/app/cmake-3.13.2_src
$ ./configure --prefix=$HOME/app/cmake-3.13.2
$ make
$ make install
```
