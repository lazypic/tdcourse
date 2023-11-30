# Git

- 소스코드의 버전 관리 및 협업하기 위해 사용하는 분산 소스코드 관리툴입니다.
- 팀간, 코드 버전관리, 백업 및 복구, 코드의 협업을 위해 필수적으로 사용되는 툴입니다.
- [Pro Git](https://git-scm.com/book/ko/v2)을 추천합니다.


## Goal

- [브런치](git_branch.md)를 사용해서 개발하는 문화 만들기
    - 예시: https://github.com/lazypic/OpenPipelineIO/branches
- 코드 PR을 하는 문화 만들기
- 기능을 위해 체계적으로 토론하는 문화 만들기
- 회사의 코드 자산 이중화
    - 물리적인 이중화
    - 서버
    - 개발자 로컬
- 항상 롤백을 할 수 있는 구조 만들기

### Reference

- Code Review rule(+2,+1): https://github.com/golang/go/issues/40699
- Company model: https://github.com/PixarAnimationStudios/OpenUSD
- Foundation model: https://github.com/AcademySoftwareFoundation/OpenImageIO
- Tracking: https://github.com/jedypod/nuke-config

## 설치

### Windows

초콜레티를 설치합니다.

```bash
choco install git
```

### Ubuntu / Debian

```bash
sudo apt-get install git
sudo apt-get install git-lfs
git lfs install
```

### RockyLinux8.5

```bash
dnf -y install git
dnf -y install git-lfs
```

### macOS

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

### Github 계정 토큰 셋팅방법

Github와 Git을 연결할 때 개인 로그인 패스워드를 사용할 수 없습니다. 토큰값이 실제로 코드리뷰에 사용하는 패스워드가 됩니다.

- Account > Settings > Developer settings > Personal access tokens > Tokens
- Generate new token > Generate new token(classic) > 인증
- 입력정보
    - repo 체크
    - note에 토큰의 용도를 타이핑한다.
    - generate token 을 누르고 해당 토큰을 복사해둔다. 이 코드가 Github 접속시 패스워드가 된다.
