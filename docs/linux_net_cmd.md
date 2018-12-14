# 네트워크 명령
리눅스에서 자주 사용하는 네트워크 명령어를 알아보겠습니다.

## ifconfig
IP를 알아낼 때 사용합니다. 소프트웨어 라이센스를 발급할 때 많이 사용합니다. 일반적으로 `b6:f6:1c:4d:2b:3c` 형태의 맥어드레스 정보를 이용해서 라이센스를 많이 발급하기 때문입니다.
맥 어드레스는 하드웨어 고유 값이기 때문에 라이센스를 발급받은 랜카드는 잘 관리해야합니다.

```bash
$ ifconfig
```

## ping
서버가 살아있는지 체크할 때 사용합니다. 옆친구의 ip를 알려달라고 하고 친구 ip로 테스트 해봅시다.

```bash
$ ping google.com
$ ping 192.168.216.106
```


## whoami
서버에 접속한 내가 누구인지 체크할 때 사용합니다.
많은 서버를 관리하다보면 자신이 누군지 해깔릴 경우가 있습니다.

```bash
$ whoami
```

## ssh
ssh로 다른 서버에 터미널로 접근하는 명령어
서버를 관리하다보면 굉장히 많이 사용하는 명령어 입니다.

woong 유저로 192.168.219.106 서버로 접근하는 예제

```bash
$ ssh woong@192.168.219.106
```

## who
내 컴퓨터에 누가 접속했는지 볼 때 사용합니다.
친구에게 자신의 컴퓨터 접근 정보를 알려주고 ssh 접속하도록 합니다.
그리고 who 명령어를 타이핑 해봅시다.

```bash
$ who
```

## wget
인터넷에서 파일을 다운로드 받을 때 많이 사용합니다.
제가 만든 trans 명령어를 wget으로 받아서 시스템에 설치해 봅시다.

```bash
$ cd ~
$ mkdir bin
$ cd bin
$ wget https://github.com/lazypic/trans/releases/download/v0.1/trans_linux.tgz
$ tar -zxvf trans_linux.tgz
$ rm trans_linux.tgz
```

## curl
URL을 이용해서 데이터를 전달하는 툴, 라이브러리 입니다.

서울 날씨를 확인해봅시다.

```bash
$ curl wttr.in/seoul
```

## scp
secure copy의 약자입니다. 네트워크를 이용해서 파일전송시 보안을 지키며 데이터를 복사할 수 있습니다.

```bash
$ scp /home/woong/image.jpg woong@192.168.219.100:/home/woong
```