# Python Redis
redis 라이브러리를 이용해서 파이썬 스크립트에서
간단하게 Key 값을 이용해서 Value 를 저장하거나 불러올 수 있습니다.

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

## Reference
- https://www.bogotobogo.com/python/python_redis_with_python.php