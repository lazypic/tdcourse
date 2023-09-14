# Git

리누스 토발즈가 만든 분산 소스코드 관리툴입니다.
인기있는 버전 관리 시스템중 하나인 Git을 설치 및 사용해보겠습니다.


## 설치

### Windows에서 Git 설치

초콜레티를 설치합니다.

```bash
choco install git
```

### Debian

```bash
sudo apt-get install git
sudo apt-get install git-lfs
git lfs install
```

### RockyLinux8.5에서 Git 설치

```bash
dnf -y install git
dnf -y install git-lfs
```

### macOS에서 Git 설치

macOS 에서는 아래처럼 명령어를 입력합니다.
Xcode Command Line Tool에 Git이 포함되어 있기 때문입니다.

```bash
xcode-select --install
brew install git-lfs
git lfs install
```

## 설정

### 개발자 설정

Git을 최초에 설치하고 사용하기 위해서는 name, e-mail 설정이 필요합니다.
가독성을 위해서 컬러 모드를 켭니다.

```bash
git config --global user.name "jason"
git config --global user.email jason@lazypic.org
git config --global color.ui true
```

### 설정값 확인

name, email 값이 잘 설정되었는지 체크합니다.

```bash
git config user.name
git config user.email
```

이제 Git을 활용할 수 있는 준비는 끝났습니다.

### 설정파일 확인하기

설정파일은 ~/.gitconfig 에 존재합니다.

vim으로 설정파일을 관찰해보세요.

```bash
vim ~/.gitconfig
```

## Github 셋팅방법

- Account > Settings > Developer settings > Personal access tokens > Tokens
- Generate new token > Generate new token(classic) > 인증
- 입력정보
    - repo 체크
    - note에 토큰의 용도를 타이핑한다.
    - generate token 을 누르고 해당 토큰을 복사해둔다. 이 코드가 github 접속시 패스워드가 된다.
