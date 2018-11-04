# VNC
회사 또는 조직에서 일하다보면 원격데스트톱 환경에서 셋팅하는 상황이 많이 발생합니다.
터미널만으로 인스톨 할 수 없는 소프트웨어도 간혹 발생합니다.
VNC 서버를 셋팅하는 방법에 대해서 알아보겠습니다.

### 서버설치
- tigervnc server를 설치합니다.
```
# yum install tigervnc-server
```

- 설정파일을 복사합니다.
```
# cp /lib/systemd/system/vncserver@.service /etc/systemd/system/vncserver@:1.service
```

- vim으로 설정파일을 열고 `<USER>` 라고 되어있는 부분을 사용자 이름으로 바꾸어주세요.
```
# vim /etc/systemd/system/vncserver@:1.service
```

- VNC 서비스를 위한 방화벽을 열어주고 방화벽을 다시 Load 합니다.
```
# firewall-cmd --permanent --zone=public --add-service vnc-server
# firewall-cmd --reload
```

- vnc에 접속할 계정으로 로그인 후, vncserver 명령어를 입력하여  패스워드 설정을 진행합니다.
```
$ vncserver                                                                                
```

- VNC 데몬을 활성화합니다.
```
# systemctl daemon-reload
# systemctl enable vncserver@:1.service
# reboot
# systemctl start vncserver@:1.service
```

### 클라이언트 설치
- macOS : https://bintray.com/tigervnc/stable/tigervnc/1.9.0
- centOS7.x
```
# yum install tigervnc
```

### 접속해보기
- tigerVNC를 이용해서 서버에 접속합니다.
- IP뒤에 `:1` 을 붙혀주세요.
```
192.168.219.105:1
```
