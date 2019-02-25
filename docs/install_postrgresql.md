# PostrgreSQL

홈페이지 : https://www.postgresql.org

## 설치
https://www.postgresql.org/download/linux/redhat/
에서 아래처럼 항목을 선택합니다.

1. Select Version : 11
1. Select Platform : CentOS7
1. Select Architecture : x86_64

다운로드 받은 rpm 파일을 yum으로 설치합니다.
```
# yum install https://download.postgresql.org/pub/repos/yum/11/redhat/rhel-7-x86_64/pgdg-centos11-11-2.noarch.rpm
# yum install postgresql11
# yum install postgresql11-server
# /usr/pgsql-11/bin/postgresql-11-setup initdb
# systemctl enable postgresql-11
# systemctl start postgresql-11
```

## 방화벽 설정
```
# firewall-cmd --zone=public --add-port=5432/tcp --permanent
# firewall-cmd --reload
```

## 외부 접속 허용
외부 ip가 여러분의 DB로 접근하기 위해서는 설정파일 수정이 필요합니다.

```
# vim /var/lib/pgsql/11/data/postgresql.conf
```

```
listen_address = “*”
```

## 암호설정
postgres DB는 postgres 사용자를 사용합니다.
psql 명령을 이용해서 DB 접속 패스워드를 입력합니다. 실습을 위해서 `postgres` 암호를 사용했지만, 나중에는 좀더 어려운 패스워드를 사용해주세요.

```
# su – postgres
> psql
\password postgres
\q
# exit
```

## 외부 접속을 위한 보안 설정

```bash
$ cd /var/lib/pgsql/10/data
$ vim pg_hba.conf
```

pg_hba.conf 파일을 아래처럼 수정합니다.

이러한 내용을..
```
local all all peer
host all all 127.0.0.1/32 ident
host all all ::1/128 ident
```

이렇게 바꾸어줍니다. 패스워드 전송을 md5 암호화를 이용하여 전송하는 설정입니다.

```
local all all md5
host all all 0.0.0.0/0 md5 // 전체 접근
host all all ::1/128 md5
```

데이터베이스를 재시작 합니다.
```
# systemctl restart postgresql-11
```

## DATABASE 생성
`projects` 이름으로 DB를 생성합니다.

```
# su – postgres
-bash-4.2$ psql
postgres=# CREATE DATABASE projects;
```


## Reference
- https://postgresdba.com/bbs/board.php?bo_table=B12&wr_id=36
