http://www.digimoon.net/blog/449

- tigervnc server를 설치합니다.
```
# yum install tigervnc-server
```

- 설정파일을 복사합니다.
```
# cp /lib/systemd/system/vncserver@.service /etc/systemd/system/vncserver@:1.service
```

- vim으로 설정파일을 열고 <USER> 라고 되어있는 부분을 로그인할 user이름으로 바꾸어주세요.
```
# vim /etc/systemd/system/vncserver@:1.service/etc/systemd/system/vncserver@:1.service
```

- 방화벽을 열어줍니다.
```
# firewall-cmd --permanent --zone=public --add-service vnc-server
# firewall-cmd --reload
```

- vnc계정 패스워드설정. 원격조정할 패스워드와 보기만 가능한 패스워드를 설정합니다.
```
$ vncserver                                                                                
```

- 데몬을 활성화
```
# systemctl daemon-reload
# systemctl enable vncserver@:1.service
# reboot
# systemctl start vncserver@:1.service
```
