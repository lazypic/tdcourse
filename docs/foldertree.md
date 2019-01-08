# 폴더 구조
리눅스를 다룸에 있어서 폴더구조 개념을 알 필요가 있습니다.

### 경로 출력하기
Root Path로 이동합니다.

```bash
$ cd /
$ ls -al
```

### 폴더설명
- bin : 리눅스 명령어가 모여있는 폴더
- boot : 리눅스 부트로더가 존재하는 폴더. grub.conf 설정시 들어가는 폴더
- dev : 시스템 장치, 하드디스크
- etc : 시스템의 설정파일이 존재하는 경로
	- /etc/passwd : 사용자관리
	- /etc/named.conf : DNS셋팅
- home : 사용자의 홈디렉토리
- lib : 리눅스 커널모듈파일, 라이브러리파일, C, C++에 필요한 라이브러리 파일
- lib64 : 위와 동일합니다.
	- CentOS7부터는 /usr/lib으로 심볼릭 링크 되어있고 64비트의 경우 /lib64 CentOS7 부터는 /usr/lib64로 링크 되어 있습니다.
- media : USB 같은 탈부착 가능한 장치들이 마운트되는 경로
- mnt : 용도는 media와 비슷하다. 임시적으로 mnt해서 사용함.
- opt : 응용 프로그램 소프트웨어 패키지에 대한 스토리지로 사용되는 곳
	- gcc 6.x 설치를 위해서 yum으로 devtoolset-6을 설치하면 이곳에 설치됩니다.
- proc : 가상파일 시스템, 메모리에 존재하는 모든 작업이 파일로 존재하는 곳.
- root : 관리자 홈디렉토리
- run : Runtime 변수 데이터. 마지막 부팅 이후 실행중인 시스템에 대한정보, 예를들어 현재 로그인한 사용자 및 실행중인 데몬정보가 있다.
- sbin : 시스템관리자들이 사용하는 관리자용 명령어를 저장하는 디렉토리
- srv : ftp, www같은 서비스에 대한 사이트 데이터가 저장되는 곳 
- sys : 2.6커널 이후 핫 플러그 하드웨어 장치 지원이 증가함에 따라서 /proc 처럼 장치의 정보를 파일로 볼 수 있는곳
- tmp : 공용 temp 디렉토리
- usr : 일반 사용자들이 주로 사용하는 디렉토리
	- /usr/bin : 일반사용자의 명령어는 이곳에 모여있습니다.
	- /usr/include : 프로그램에 필요한 헤더파일(.h)이 있습니다.
	- /usr/lib : /lib 에 들어가지 않는 라이브러리가 존재합니다.
	- /usr/src : 프로그램 소스가 저장되는 곳 입니다.
	- /usr/local : 일반 어플리케이션들이 컴파일할 때 사용되는 장소 입니다.
	- /usr/share/man : 리눅스 메뉴얼이 존재합니다.
- var : 시스템 운용중에 생성되었다가 삭제되는 데이터를 일시적으로 저장할 때 사용되는 경로
	- /var/log : 시스템 로그파일
	- /var/named : DNS Zone 설정
	- /var/spool/mail : 메일
	- /var/spool/cron : cron 설정파일

## Reference
- Filesystem Hierarchy Standard : http://www.pathname.com/fhs/pub/fhs-2.3.html#LIBESSENTIALSHAREDLIBRARIESANDKERN
