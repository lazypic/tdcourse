# 환경변수
프로세스가 컴퓨터에서 동작될 때 영향을 미치는 값

### 시스템에 설정된 환경변수
env 명령은 이미 선언된 환경변수를 보여주는 명령어 입니다.

```
$ env
```

### 시스템에 예약된 환경변수
```
$ echo $HOME
작성해보기..
```

### .bashrc
Bash쉘을 사용할 때 bash가 참고할 정보를 정의한 파일입니다.
파일의 위치는 `~/.bashrc` 입니다.
이곳에 환경변수 또는 사용자 alias를 설정해서 사용합니다.

### alias
linux 환경에 긴 명령어나 값을 간단하게 줄여서 설정한 값.
회사에서는 모두가 자주 사용하는 소프트웨어를 실행할 때
alias를 만들어서 간단하게 타이핑후 실행되도록 만듭니다.

.bashrc 파일에 아래처럼 정의해 보세요.
```
alias weather="curl wttr.in/seoul"
```

### export
특정값을 환경변수로 설정할 수 있습니다.

아래 예제는 OCIO 환경변수에 `~/OpenColorIO-configs/aces_1.0.3/config.ocio` 값을 설정하는 예제입니다.
```
export OCIO=$HOME/OpenColorIO-Configs/aces_1.0.3/config.ocio
```

### source
설정파일을 불러올 때 사용합니다.

홈디렉토리에 환경변수, alias가 정의된 custom.bash 파일이 있다면,
source를 이용해서 부를 수 있습니다.

```
$ source ~/custom.bash
```
