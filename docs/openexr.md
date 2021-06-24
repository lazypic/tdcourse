# OpenEXR
오픈소스 이미지 저장 포멧이며 ILM에서 제작되었습니다.
현재 ACES 표준 포멧입니다. VFX에서 굉장히 많이 사용됩니다.

- 홈페이지 : http://www.openexr.com
- 소스코드 : https://github.com/AcademySoftwareFoundation/openexr

## 기본버전 설치
yum을 이용하여 간단하게 낮은 버전의 OpenEXR을 설치할 수 있습니다.

```bash
$ sudo yum install OpenEXR
$ sudo yum install OpenEXR-libs
```


## OpenEXR 컴파일하기.
높은 버전의 OpenEXR을 이용하기 위해서는 직접 컴파일후 사용해야 합니다.

- git을 이용해서 OpenEXR 소스코드를 다운로드 합니다.

```bash
$ cd ~/app
$ wget https://github.com/AcademySoftwareFoundation/openexr/archive/refs/tags/v2.5.7.tar.gz
$ tar -zxvf v2.5.7.tar.gz
$ rm v2.5.7.tar.gz
$ mv openexr-2.5.7 openexr-2.5.7_src
```

#### IlmBase 컴파일
- 먼저 IlmBase 라이브러리를 컴파일 하겠습니다. IlmBase 폴더로 이동합니다.
```bash
$ cd ~/app/openexr-2.5.7_src/IlmBase
```

- configure 파일을 생성하기 위해서 bootstrap을 타이핑합니다.
```bash
$ sudo yum install autoconf # bootstrap은 autoconf 툴을 필요로 합니다.
$ sudo yum install automake # automake를 설치하면 bootstrap에 사용되는 aclocal 명령어가 설치됩니다.
$ sudo yum install libtool # libtool을 설치하면 bootstrap에 사용되는 libtoolize 명령어가 설치됩니다.
$ ./bootstrap
```
- bootstrap이 잘 실행되었다면, configure 파일이 생성됩니다.
- configure 파일을 실행합니다. --prefix 옵션을 달아서 어디로 컴파일 할것인지 옵션을 설정하세요.
- gcc9 이상 사용을 위해서 devtoolset-9 설정을 해줍니다.
```
$ scl enable devtoolset-9 bash
$ ./configure --prefix=$HOME/app/IlmBase
$ make
$ make install
```

- 잘 배포되면 ~/app/IlmBase 경로에 include, lib 폴더가 생성되어 있습니다.
- ~/app/IlmBase 경로에 컴파일된 라이브러리는 다른 프로그램 컴파일시 `--with-ilmbase-prefix` 또는 `ILMBASE_HOME`등 키값에 대한 변수로 사용할 수 있습니다.

#### OpenEXR 컴파일
- 위와 같은 방식으로 똑같이 OpenEXR 컴파일을 진행합니다.
- prefix경로는 `~/app/OpenEXR`로 설정하겠습니다.

```bash
$ cd ~/app/openexr-2.5.7_src/OpenEXR
$ scl enable devtoolset-9 bash
$ ./bootstrap
$ ./configure --prefix=$HOME/app/openexr-2.5.7 --with-ilmbase-prefix=$HOME/app/IlmBase
$ make
$ make install
```

#### prefix 경로 확인
- ~/app/openexr 경로에 bin, include, lib, share 경로가 생성됩니다.


#### 컴파일된 OpenEXR 관련 명령어 실행전에 lib 불러오기
컴파일된 파일을 실행하기 전에 LD_LIBRARY_PATH에 openexr lib 디렉토리를 추가해야합니다.

```bash
$ export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$HOME/app/openexr-2.5.7/lib
```


## 참고 : Bootstrap이란?

리눅스에서 사용하는 자동화 툴은 많이 있습니다. make는 파일 내용중 하나가 변경되면 적절한 순서로 적절한 프로그램을 실행하도록 도와주는 툴입니다. 문제는  소프트웨어가 거대해지면서 컴파일시 의존성과 순서를 기억하기는 어렵습니다.
이때 의존성, 절차를 도와주는 의존적인 도구들이 아래에 몇가지 존재합니다.

- automake
- autoconf
- libtool