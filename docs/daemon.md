# Daemon

우리가 지금껏 배웠던 리눅스에서 사용하는 일반 명령어들은 타이핑하면 바로 실행되었습니다. 원하는 기능을 수행하고 종료되는 명령어 였습니다.
데몬은 시스템에서 항상 실행중인 프로그램들을 뜻합니다.
데몬이라 부르기도 하고 서비스라고 불리기도 합니다.

일반적으로 서버 프로그램들은 데몬입니다.

## 시스템 서비스 확인하기

```bash
# setup
```

## 웹서버 설치 및 실행

아파치 웹서버를 설치합니다.

```bash
# yum install httpd
```

아파치 웹서버를 활성화하고 서비스를 재시작 합니다.

```bash
# systemctl enable httpd.service
# systemctl restart httpd.service
```

방화벽 때문에 아직 웹서버에 접근할 수 없습니다.
http, https 서비스를 허용하고 방화벽을 재시작 해줍니다.

```bash
# firewall-cmd --add-service=http --permanent
# firewall-cmd --add-service=https --permanent
# firewall-cmd --reload
```

실습은 기본설정으로 진행합니다.
나중에 추가적으로 셋팅하고 싶다면 아파치 웹서버 설정파일은 아래경로에 위치합니다.

```bash
$ vim /etc/httpd/conf/httpd.conf
```

설정파일을 수정했다면 서비스를 제시작 해주세요.

```bash
# systemctl restart httpd.service
```

## 웹사이트 만들어 보기
지금 아주 간단한 웹서버를 만들어 보겠습니다. 이 스킬은 나중에 맨 후반에 github.io 부분을 다룰 때 도움이 됩니다.

/var/www/html/index.html 문서를 만들어보세요.

```
# vim /var/www/html/index.html
```

index.html 파일내용
```html
<html>
<head>
<title>Hello World!</title>
</head>
<body>Hello World!</body>
</html>
```
