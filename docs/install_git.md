# Git
리누스 토발즈가 만든 버전관리 시스템입니다.
버전 관리 시스템중 하나인 Git을 설치 및 사용해보겠습니다.

## RockyLinux8.5에서 Git 설치

```bash
dnf install git
```

## macOS에서 Git 설치
macOS 에서는 아래처럼 명령어를 입력합니다.
Xcode Command Line Tool에 Git이 포함되어 있기 때문입니다.
\
```bash
$ xcode-select --install
```

## Windows에서 Git 설치
Windows : https://git-scm.com/downloads 에서 다운로드 받아 설치합니다.

### 최초 셋팅
Git을 최초에 설치하고 사용하기 위해서는 name, e-mail 설정이 필요합니다.
가독성을 위해서 컬러 모드를 켭니다.

```bash
$ git config --global user.name "woong"
$ git config --global user.email khw7096@gmail.com
$ git config --global color.ui true
```

### 설정값 확인
name, email 값이 잘 설정되었는지 체크합니다.

```bash
$ git config user.name
$ git config user.email
```

이제 Git을 활용할 수 있는 준비는 끝났습니다.

### 설정파일
설정파일은 ~/.gitconfig 에 존재합니다.

vim으로 설정파일을 관찰해보세요.
```
$ vim ~/.gitconfig
```

### GUI Clients
기본적으로 Git 명령어를 이용해서 소스코드를 관리할 수 있습니다.
또한 GUI툴을 활용할 수 도 있습니다.
- https://git-scm.com/download/gui/linux
