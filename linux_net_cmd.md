# 네트워크 명령
### ifconfig
IP를 알아낼 때 사용합니다.

### ping
서버가 살아있는지 체크할 때 사용합니다.

```
$ ping google.com
$ ping 192.168.216.106
```

### who
내 컴퓨터에 누가 접속했는지 볼 때 사용합니다. 

```
$ who
```

### whoami
서버에 접속한 내가 누구인지 체크할 때 사용합니다.
많은 서버를 관리하다보면 자신이 누군지 해깔릴 때가 있어요.

```
$ whoami
```

### ssh
ssh로 다른 서버에 터미널로 접근하는 명령어
서버를 관리하다보면 굉장히 많이 사용하는 명령어 입니다.

woong 유저로 192.168.219.106 서버로 접근하는 예제
```
$ ssh woong@192.168.219.106
```

### wget
인터넷에서 파일을 다운로드 받을 때 많이 사용합니다.
제가 만든 trans 명령어를 wget으로 받아서 시스템에 설치해 봅시다.

```
# cd /tmp
# wget https://github.com/lazypic/trans/releases/download/v0.1/trans_linux.tgz
# tar -zxvf trans_linux.tgz
# mv ./trans /bin
# rm ./trans_linux.tgz
```

### curl
URL을 이용해서 데이터를 전달하는 툴, 라이브러리 입니다.

서울 날씨를 확인해봅시다.
```
$ curl wttr.in/seoul
```
