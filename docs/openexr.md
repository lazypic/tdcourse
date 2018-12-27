# OpenEXR
오픈소스이며, ILM에서 만든 이미지 저장포멧입니다.
현재 ACES 표준 포멧입니다.
VFX에서 많이 사용됩니다.

2000년도에 8비트,10비트를 넘어 보다 더 많은 정보를 담기 위한 목적으로 제작된 포멧입니다.

- 홈페이지 : http://www.openexr.com
- 소스코드 : https://github.com/openexr/openexr

## 설치
yum을 이용하여 간단하게 OpenEXR을 설치할 수 있습니다.

```
yum install OpenEXR
yum install OpenEXR-libs
yum install OpenEXR-devel
```


## OpenEXR 컴파일하기.

- git을 이용해서 OpenEXR 소스코드를 다운로드 합니다.
```
$ cd ~/app
$ git clone https://github.com/openexr/openexr openexr_src
```

#### IlmBase 컴파일
- 먼저 IlmBase 라이브러리를 컴파일 하겠습니다. IlmBase 폴더로 이동합니다.
```
$ cd openexr_src/IlmBase
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
$ 
```
- make 명령을 이용해서 컴파일 합니다.
```
$ make
```
- make 컴파일된 명령어를 prefix 경로로 배포합니다.
```
$ make install
```

- 잘 배포되면 ~/app/IlmBase 경로에 include, lib 폴더가 생성되어 있습니다.
- ~/app/IlmBase 경로는 다른 라이브러리 또는 프로그램 컴파일시 `--with-ilmbase-prefix`, `ILMBASE_HOME`등 키값에 대한 변수로 사용할 수 있습니다.

#### OpenEXR 컴파일
- 위와 같은 방식으로 똑같이 OpenEXR 컴파일을 진행합니다.
- prefix경로는 `~/app/OpenEXR`로 설정하겠습니다.
```
$ cd openexr_src/OpenEXR
$ scl enable devtoolset-6 bash
$ ./bootstrap
$ ./configure --prefix=$HOME/app/OpenEXR --with-ilmbase-prefix=$HOME/app/IlmBase
$ make
$ make install
```

#### prefix 경로 확인
- ~/app/OpenEXR 경로에 bin, include, lib, share 경로가 생성됩니다.
