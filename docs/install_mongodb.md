# mongoDB
mongoDB를 설치해보겠습니다.

## 설치

```
# vim /etc/yum.repos.d/mongodb-org.repo
```

monogdb-org.repo 내용은 아래처럼 작성합니다.
```
[mongodb-org-4.0]
name=MongoDB Repository
baseurl=https://repo.mongodb.org/yum/redhat/$releasever/mongodb-org/4.0/x86_64/
gpgcheck=1
enabled=1
gpgkey=https://www.mongodb.org/static/pgp/server-4.0.asc
```

관리자에서 yum을 이용하여 설치합니다.
```
# yum install -y mongodb-org
```

## mongoDB의 데이터 및 로그 폴더
DB를 운용하기 위해서는 아래 2가지 폴더를 알고 있다면 좋습니다.

- /var/lib/mongo : 데이터
- /var/log/mongodb : 로그

## 방화벽 설정
```
# firewall-cmd --zone=public --add-port=27017/tcp --permanent
success
# firewall-cmd --reload
```

## 서비스 시작
```
# service mongod start
# cat /var/log/mongodb/mongod.log
```

재부팅시 자동으로 mongodb 서버가 실행되려면 아래 명령어를 타이핑 해주세요.
```
# chkconfig mongod on
```

## mongod.conf 데이터베이스 설정변경
/etc/mongod.conf 파일을 수정해줍니다.
```
# vim /etc/mongod.conf
```

bindIpAll값을 net에 추가해줍니다. 이렇게 해야 자신의 ip를 이용해서 다른 컴퓨터가 접속할 수 있습니다.
```
net:
  port:27017
  bindIpAll: true
  #bindIp: 127.0.0.1
```

설정값을 수정했다면 mongod를 재시작해줍니다.
```
# service mongod restart
```

서비스를 중지했다가 다시 실행하도 좋습니다.
```
# service mongod stop
# service mongod start
```

## DB 쉘 접속하기
mongod가 잘 작동되는지 체크해봅시다. 아래처럼 터미널에서 타이핑 해보세요.
```
$ mongo
```

## Reference
- https://docs.mongodb.com/manual/tutorial/install-mongodb-on-red-hat/


# macOS
macOS에서 mongoDB를 설치하는 방법

```bash
$ brew install mongodb
```

## 서비스 시작
```bash
$ brew services start mongodb
```