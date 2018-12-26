# 환경변수
프로세스가 컴퓨터에서 동작될 때 영향을 미치는 값입니다.

## 시스템에 설정된 환경변수
env 명령은 이미 선언된 환경변수를 보여주는 명령어 입니다.

```
$ env
```

## 시스템에 예약된 환경변수
자주 사용되는 환경변수를 확인해보겠습니다.

```
$ echo $HOME
$ echo $USER
$ echo $PATH
```

## .bashrc
Bash쉘을 사용할 때 bash가 참고할 정보를 정의한 파일입니다.
파일의 위치는 `~/.bashrc` 입니다.
이곳에 환경변수 또는 사용자 alias를 설정해서 사용합니다.

## alias
linux 환경에 긴 명령어나 값을 간단하게 줄여서 설정한 값입니다.
회사에서는 모두가 자주 사용하는 소프트웨어를 실행할 때
alias를 만들어서 간단하게 타이핑후 실행되도록 만듭니다.

~/.bashrc 파일에 alias를 지정하면 명령어를 사용할 수 있습니다.
저는 개인적으로 제가 자주 주문하는 중국집을 alias로 잡아보겠습니다.

```
alias 차이홍="echo 031-916-8867"
```

말도 하게 해보죠. 컴퓨터가 말을 하려면 espeak를 설치합니다.

~/.bashrc
```bash
$ su
# yum install espeak
```

다시한번 알리아스를 수정해 보겠습니다.

~/.bashrc
```
alias 차이홍="echo 031-916-8867 && espeak 'The contact number for Chinese restaurant is 0319168867.'"
```

## export
특정경로를 환경변수로 설정할 수 있습니다.

아래 예제는 OCIO 환경변수에 `$HOME/OpenColorIO-configs/aces_1.0.3/config.ocio` 값을 설정하는 예제입니다.

~/.bashrc
```
export OCIO=$HOME/OpenColorIO-Configs/aces_1.0.3/config.ocio
```

OCIO는 OpenColorIO의 약자이며 이 환경변수를 가지고 추후 컬러매니징을 다루게 됩니다.

## source
설정파일을 불러올 때 사용합니다.

환경변수, alias가 정의된 custom.bash 파일이 있다면,
source 명령어를 이용해서 파일에 선언된 환경변수를 부를 수 있습니다.

~/env/custom.env
```bash
PROJECT=CIRCLE
SHOT=FOO_0010
```

터미널에서 값이 잘 인식되는지 확인합니다.
```bash
$ source $HOME/env/custom.env
$ echo $PROJECT
$ echo $SHOT
```
