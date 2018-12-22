# PostrgreSQL

홈페이지 : https://www.postgresql.org

## 설치
https://www.postgresql.org/download/linux/redhat/
에서 항목을 선택합니다.

```
# yum install https://download.postgresql.org/pub/repos/yum/11/redhat/rhel-7-x86_64/pgdg-centos11-11-2.noarch.rpm
# yum install postgresql11
# yum install postgresql11-server
# /usr/pgsql-11/bin/postgresql-11-setup initdb
# systemctl enable postgresql-11
# systemctl start postgresql-11
```

## 방화벽
```
# firewall-cmd -–zone=public -–add-port=5432/tcp --permanent
# firewall-cmd --reload
```

## 외부 접속 허용
```bash
$ vim /var/lib/pgsql/11/data/postgresql.conf
```

```
listen_address = “*”
```

## 암호설정
```
# su – postgres
> psql
\password postgres
\q
# exit
```

## 외부 접속을 위한 보안 설정
cd /var/lib/pgsql/10/data
vi pg_hba.conf
(편집 내용)
local all all peer 문자열을 local all all md5 로 변경
host all all 127.0.0.1/32 ident 문자열을 host all all 0.0.0.0/0 md5 로 변경
host all all ::1/128 ident 문자열을 host all all ::1/128 md5 로 변경

```
# systemctl restart postgresql-11
```

## DATABASE 생성
```
# su – postgres
-bash-4.2$ psql
postgres=# CREATE DATABASE projects;
```