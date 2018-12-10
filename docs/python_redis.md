# Python Redis
redis 라이브러리를 이용해서 파이썬 스크립트에서
간단하게 Key 값을 이용해서 Value 를 저장하거나 불러올 수 있습니다.
메모리에서 DB가 작동되기 때문에 굉장히 속도가 빠릅니다.

## 설치
터미널에서 아래처럼 타이핑합니다.

```bash
# pip install redis
```

## 예제
```python
#coding:utf8
import redis

r = redis.Redis(
    host='192.168.219.105',
    port=6379)
r.set('foo', 'bar') # 값을 설정하기
value = r.get('foo') # 값을 가지고 오기
print(value)
r.set('foo', 'foo') # 값을 수정하기
value = r.get('foo') # 값을 가지고 오기
print(value)
```

값을 올리는 예제
```python
import redis
r = redis.Redis(host='192.168.219.105',port=6379)
r.set('count',0)
r.incr('count') #+1
print(r.get('count'))
```

## 응 용
저는 보통 중요하지 않지만 집계가 필요한 상황에서 Redis를 사용하기를 선호합니다.

- 오늘 하루 아티스트가 몇번 뉴크를 실행했는가?
- 특정 어플리케이션이 오늘 회사 전체에서 몇번 실행되었는가?
- 툴의 설정값을 사용자 자리에 저장하지 않고 서버에 저장하고 싶을 때
    - OS마다 경로문제가 복잡할 때 차라리 Server에 값을 저장하는 것이 편리할 때가 있습니다.

## Reference
- https://www.bogotobogo.com/python/python_redis_with_python.php