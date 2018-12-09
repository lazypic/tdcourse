# Daemon

일반 명령어는 필요시에 타이핑해서 실행했었지만,
데몬은 시스템에 항상 실행중인 프로그램들을 뜻한다.
데몬이라 부르기도 하고 서비스라고 불리기도 한다.

일반적으로 서버 프로그램들이 데몬인 경우가 많다.

### 시스템 서비스 확인하기
```
# setup
```

### 웹서버 설치 및 실행
아파치 웹서버를 설치합니다.
```
# yum install httpd
```

아파치 웹서버를 활성화하고 서비스를 재시작 합니다.
```
# systemctl enable httpd.service
# systemctl restart httpd.service
```

방화벽 때문에 아직 웹서버에 접근할 수 없습니다.
http, https 서비스를 허용하고 방화벽을 재시작 해줍니다.
```
# firewall-cmd --add-service=http --permanent
# firewall-cmd --add-service=https --permanent
# systemctl restart firewalld
```

참고로 웹서버의 설정파일은 아래 경로에 있습니다.
```
$ vim /etc/httpd/conf/httpd.conf
```

### 웹사이트 만들어 보기

/var/www/html/index.html 문서를 만들어보세요.
