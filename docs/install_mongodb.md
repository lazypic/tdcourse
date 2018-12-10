# mongoDB
mongoDB를 설치해보겠습니다.

## 설치
```
# vim /etc/yum.repos.d/mongodb-org.repo
```

```
[mongodb-org-4.0]
name=MongoDB Repository
baseurl=https://repo.mongodb.org/yum/redhat/$releasever/mongodb-org/4.0/x86_64/
gpgcheck=1
enabled=1
gpgkey=https://www.mongodb.org/static/pgp/server-4.0.asc
```

```
# yum install -y mongodb-org
```

## mongoDB의 데이터 및 로그 폴더
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

## mongod.conf 설정변경
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

설정값이 바뀌었습니다. mongod를 재시작해줍니다.
```
# service mongod restart
```

## 쉘로 들어가기
mongod가 잘 작동되는지 체크해봅시다. 아래처럼 터미널에서 타이핑 해보세요.
```
$ mongo
```

## 서비스 중지 / 재시작
```
# service mongod stop
# service mongod restart
```

## Reference
- https://docs.mongodb.com/manual/tutorial/install-mongodb-on-red-hat/