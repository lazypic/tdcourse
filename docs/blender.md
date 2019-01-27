# Blender
블랜더 2.8을 설치하는 방법을 알아보겠습니다.
CentOS7.6의 glibc 버전은 낮습니다.

블랜더 2.80 베타는 glibc2.24를 요구합니다.
blender-2.80-1b6da95ccb11-linux-glibc224-x86_64

이름을 관찰하면 glibc2.24를 이용해서 컴파일된 정보를 확인할 수 있습니다.

블랜더2.8 베타를 실행하려면 libmvec.so 파일이 필요합니다.
관련된 파일을 컴파일 하는 방법을 다룹니다.

```
$ cd ~
$ cd app
$ mkdir glibc
$ wget https://ftp.gnu.org/gnu/libc/glibc-2.24.tar.gz
$ tar -xvzf ./glibc-2.24.tar.gz
$ cd glibc-2.24
$ mkdir build
$ cd build
$ ../configure --enable-kernel=3.10 --prefix=$HOME/app/glibc
```

kernel version check
```
$ uname -a
```

blender 실행파일이 있는 곳에서 아래처럼 타이핑 합니다.
```
$ cd lib
$ ln -s $HOME/app/glibc-2.24/build/lib/libmvec.so ./libmvec.so.1
$ ln -s $HOME/app/glibc-2.24/build/lib/libm.so ./libm.so.6
```

## Reference
- https://blender.stackexchange.com/questions/120890/blender-2-8-cannot-find-libmvec-so-1https://blender.stackexchange.com/questions/120890/blender-2-8-cannot-find-libmvec-so-1