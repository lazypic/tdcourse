# Redis

## 설치
```
# yum install redis
```

서비스시작, 재부팅시 자동실행
```
# systemctl start redis
# systemctl enable redis
```

## 실행
```
redis-cli ping
```

아래처럼 출력되면 정상입니다.
```
PONG
```

## redis.conf 셋팅
```
# vim /etc/redis.conf
```

아이피를 추가해주세요.
```
appendonly yes
appendfsync everysec
bind 127.0.0.1 192.168.219.105
```

```
# systemctl restart redis
```

## redis-cli 테스트
```
$ redis-cli
127.0.0.1:6379> set 'a' 1
OK
127.0.0.1:6379> get 'a'
"1"
```
## 방화벽설정
```
# firewall-cmd --zone=public --add-port=6379/tcp --permanent
# firewall-cmd --reload
```

## Reference
https://www.linode.com/docs/databases/redis/install-and-configure-redis-on-centos-7/