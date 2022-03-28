
# Cockpit

웹브라우저를 이용해서 터미널로 서버를 제어할 때 Cockpit을 사용하면 쉽습니다.

AWS에서 Rockylinux 설치후

```bash
sudo systemctl enable --now cockpit.socket
```

하면 Cockpit이 실행됩니다.

AWS 보안설정에서 9090 포트를 열어주세요.

루트계정의 패스워드를 변경합니다.

```bash
sudo passwd root
```

https://serverip:9090 으로 접근후 사용자 id와 패스워드를 입력하면 cockpit을 사용할 수 있습니다.

#### Reference
https://cockpit-project.org/running