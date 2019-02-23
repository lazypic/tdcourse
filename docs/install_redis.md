# Redis
파이썬 딕셔너리 구조처럼 키, 값을 간단하게 저장할 수 있는 DB입니다.
메모리에 데이터를 저장하기 때문에 굉장히 속도가 빠릅니다.

## 설치
```
# yum install redis
```

서비스시작, 재부팅시 자동실행하도록 설정하는 방법은 아래와 같습니다.
```
# systemctl start redis
# systemctl enable redis
```

## 실행
redis를 테스트하는 방법은 아래와 같습니다.
```
$ redis-cli ping
```

아래처럼 출력되면 정상입니다.
```
PONG
```

## redis.conf 셋팅
```
# vim /etc/redis.conf
```

여러분의 IP를 추가해주세요. 저는 `192.168.219.105`를 추가했습니다.
이렇게 작성하면 다른 컴퓨터에서 해당 IP로 접근할 수 있게 됩니다.

```
appendonly yes
appendfsync everysec
bind 127.0.0.1 192.168.219.105
```

설정을 바꾸었으니 Redis DB를 재시작 합니다.

```
# systemctl restart redis
```

## redis-cli 테스트
간단하게 터미널에서 Redis DB가 잘 작동하는지 테스트 해보겠습니다.

```bash
$ redis-cli
127.0.0.1:6379> set 'a' 1
OK
127.0.0.1:6379> get 'a'
"1"
```

## 방화벽설정
외부컴퓨터가 Redis DB에 접근할 수 있도록 하기 위해서는 6379 포트를 허용해야 합니다.
터미널에서 방화벽은 아래명령어로 설정할 수 있습니다.

```
# firewall-cmd --zone=public --add-port=6379/tcp --permanent
# firewall-cmd --reload
```

- --permanent : 1회가 아닌 앞으로 계속 이 옵션을 허용할 때 사용합니다.
- --zone : 서버의 용도 따라 설정된 보안레벨을 의미합니다. 사용자가 설정, 삭제, 추가가 가능합니다.


## Reference
https://www.linode.com/docs/databases/redis/install-and-configure-redis-on-centos-7/
