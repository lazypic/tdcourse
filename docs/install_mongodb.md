# mongoDB
mongoDB를 설치해보겠습니다.

# CentOS7

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

```bash
$ sudo service mongod start
$ sudo cat /var/log/mongodb/mongod.log
```

재부팅시 자동으로 mongodb 서버가 실행되려면 아래 명령어를 타이핑 해주세요.

```bash
$ sudo chkconfig mongod on
```

## mongod.conf 데이터베이스 설정변경
/etc/mongod.conf 파일을 수정해줍니다.

```bash
$ vim /etc/mongod.conf
```

bindIpAll값을 net에 추가해줍니다. 이렇게 해야 자신의 ip를 이용해서 다른 컴퓨터가 접속할 수 있습니다.

```
net:
  port:27017
  bindIpAll: true
  #bindIp: 127.0.0.1
```

설정값을 수정했다면 mongod를 재시작해줍니다.

```bash
$ sudo service mongod restart
```

서비스를 중지했다가 다시 실행하도 좋습니다.

```bash
$ sudo service mongod stop
$ sudo service mongod start
```

## DB 쉘 접속하기
mongod가 잘 작동되는지 체크해봅시다. 아래처럼 터미널에서 타이핑 해보세요.

```bash
$ mongo
```

## Reference
- https://docs.mongodb.com/manual/tutorial/install-mongodb-on-red-hat/


# RockyLinux 8.5

설치전에 dnf를 업데이트 합니다.

```bash
sudo dnf update -y
```

mongoDB 리포지터리를 추가합니다.

RockyLinux는 vim 명령어가 작동하지 않습니다. vi 명령어를 이용합니다.

```bash
sudo vi /etc/yum.repos.d/mongodb.repo
```

아래 내용을 추가해줍니다.

```
[mongodb-org-4.4]
name=MongoDB Repository
baseurl=https://repo.mongodb.org/yum/redhat/$releasever/mongodb-org/4.4/x86_64/
gpgcheck=1
enabled=1
gpgkey=https://www.mongodb.org/static/pgp/server-4.4.asc
```

추가이후 dnf update를 해주면 추가한 리포지터리에 대한 업데이트를 진행합니다.

```bash
sudo dnf update
```

다음과 같이 메시지가 출력됩니다.

```
MongoDB Repository                                                        44 kB/s |  37 kB     00:00    
종속성이 해결되었습니다.
처리가 필요하지 않습니다.
완료되었습니다!
```

mongoDB를 설치합니다.

```bash
sudo dnf install mongodb-org
```

버전을 체크합니다.

```bash
mongod --version
```

```bash
sudo systemctl status mongod # 상태를 체크합니다. 
sudo systemctl start mongod # DB를 시작합니다.
sudo systemctl enable mongod # 재부팅 되더라도 자동으로 실행될 수 있도록 합니다.
sudo systemctl status mongod # 잘 설정되어있는지 체크합니다.

sudo tail /var/log/mongodb/mongod.log # 로그를 확인합니다.
mongo # 쉘이 정상적으로 들어가지는지 체크합니다.
```

# macOS
macOS에서 mongoDB를 설치하는 방법

## 설치

```bash
$ brew uninstall mongodb
$ brew tap mongodb/brew
$ brew install mongodb-community
```

## 서비스 시작

```bash
$ brew services start mongodb-community
```
