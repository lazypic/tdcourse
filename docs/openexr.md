# OpenEXR
오픈소스이며, ILM에서 만든 이미지 저장포멧입니다.
현재 ACES 표준 포멧입니다.
VFX에서 굉장히 많이 사용됩니다.

2000년도에 8비트,10비트를 넘어 보다 더 많은 정보를 담기 위한 목적으로 제작된 포멧입니다.

- 홈페이지 : http://www.openexr.com
- 소스코드 : https://github.com/openexr/openexr

## 설치
yum을 이용하여 간단하게 낮은 버전의 OpenEXR을 설치할 수 있습니다.

```
# yum install OpenEXR
# yum install OpenEXR-libs
```


## OpenEXR 컴파일하기.
높은 버전의 OpenEXR을 이용하기 위해서는 직접 컴파일후 사용해야 합니다.
- git을 이용해서 OpenEXR 소스코드를 다운로드 합니다.
```
$ cd ~/app
$ wget https://github.com/openexr/openexr/archive/v2.3.0.tar.gz
$ tar -zxvf v2.3.0.tar.gz
$ cd openexr-2.3.0
```

#### IlmBase 컴파일
- 먼저 IlmBase 라이브러리를 컴파일 하겠습니다. IlmBase 폴더로 이동합니다.
```
$ cd ~/app/openexr-2.3.0/IlmBase
```

- configure 파일을 생성하기 위해서 bootstrap을 타이핑합니다.
```
$ ./bootstrap
```
- bootstrap이 잘 실행되었다면, configure 파일이 생성됩니다.
- configure 파일을 실행합니다. --prefix 옵션을 달아서 어디로 컴파일 할것인지 옵션을 설정하세요.
- gcc6 이상 사용을 위해서 devtoolset-6 설정을 해줍니다.
```
$ scl enable devtoolset-6 bash
$ ./configure --prefix=$HOME/app/IlmBase
$ make
$ make install
```

- 잘 배포되면 ~/app/IlmBase 경로에 include, lib 폴더가 생성되어 있습니다.
- ~/app/IlmBase 경로는 다른 라이브러리 또는 프로그램 컴파일시 `--with-ilmbase-prefix`, `ILMBASE_HOME`등 키값에 대한 변수로 사용할 수 있습니다.

#### OpenEXR 컴파일
- 위와 같은 방식으로 똑같이 OpenEXR 컴파일을 진행합니다.
- prefix경로는 `~/app/OpenEXR`로 설정하겠습니다.
```
$ cd ~/app/openexr-2.3.0/OpenEXR
$ scl enable devtoolset-6 bash
$ ./bootstrap
$ ./configure --prefix=$HOME/app/openexr --with-ilmbase-prefix=$HOME/app/IlmBase
$ make
$ make install
```

#### prefix 경로 확인
- ~/app/openexr 경로에 bin, include, lib, share 경로가 생성됩니다.

## 참고 : bootstrap이란?

리눅스에서 사용하는 자동화 툴은 많이 있습니다. make는 파일 내용중 하나가 변경되면 적절한 순서로 적절한 프로그램을 실행하도록 도와주는 툴입니다. 문제는  소프트웨어가 거대해지면서 컴파일시 의존성과 순서를 기억하기는 어렵습니다.
이때 의존성, 절차를 도와주는 파일(툴)이 몇가지 존재합니다.

- autogen 파일
- bootstrap 파일
- autoconf 파일

위 3개 파일은 서로 다른 프로젝트이지만 비슷한 역할을 합니다.

- 참고 : http://www.sourceware.org/autobook/autobook/autobook_43.html