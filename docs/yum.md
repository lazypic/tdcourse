# Yum
Yum(Yellowdog Updater Modified)은 Red Hat 리눅스 계열에서 사용하는 패키지 매니징 툴입니다.
이 툴을 이용해서 리눅스에 패키지를 검색, 설치, 삭제 할 수 있습니다.

리눅스에서는 yum 이외에도 많은 패키지 툴이 존재합니다.
우리가 사용하는 CentOS는 Red Hat 계열이라서 yum 을 사용합니다.

## 패키지툴의 종류
- RPM ( Red Hat Package Manager)
	- yum ( Yellowdog Updater, Modified)
	- dnf ( Dandified Yum ) : yum 을 대체할 차세대 패키징툴, Fedora22 부터는 DNF가 yum 대신 사용됩니다.
- DPKG ( Debian Package Management System )
	- apt(Advanced Packaging Tool) : apt-get 시리즈
	- Aptitude Package Manager
	- Synaptic Package Manager
- Arch Linux : Packman Package manager
- OpenSuse : Zypper Package Manager
- Gentoo : Portae Package Manager


## EPEL 설치
CentOS7을 설치하더라도 yum 명령어를 통해서 패키지를 설치할 때,
원하는 결과가 나오지 않습니다.
EPEL(Extra Packages for Enterprise Linux) 리포지터를 추가하면 많은 패키지를 설치할 수 있습니다.

```
# yum install epel-release
```

## 실습

앞으로 우리가 사용할 버전관리툴 git을 설치하면서 옵션들을 살펴보겠습니다.
yum은 관리자의 권한이 필요합니다. 관리자로 로그인하고 시작해주세요.

### 검색

```bash
$ su
# yum search git
```

### 설치
```bash
# yum install git
```

### 업데이트
```bash
# yum update git
# yum update # 전체 패키지에 대해서 update를 수행합니다. 오래걸립니다.
```

### 삭제
```bash
# yum remove git
```


