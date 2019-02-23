# mongoDB 실습

mongoDB는 documents 형태로 데이터를 저장합니다.

## pymongo 라이브러리 설치

```bash
$ pip install --user pymongo
```

## 실습

#### 데이터 넣기
projects 라는 DB에 circle 이라는 가상프로젝트 컬랙션을 만들고 간단한 샷 item을 하나 추가하는 예제입니다.

이 예제는 심플하게 값이 DB로 들어가도록 설정되어있습니다.
계속 코드를 실행하면 값이 중복으로 들어갑니다.
실제로 구현할 때는 중복값이 존재하는지 체크할 필요가 있습니다.

```python
from pymongo import MongoClient
import datetime

client = MongoClient("192.168.219.105", 27017)
db = client.projects
project = "circle"
date = datetime.datetime.now().strftime("%Y-%m-%dT%H:%M:%S")
item = {"name":"BAR_0010",
	"text":"fire and sky artwork",
	"tags": ["fire", "sky"],
	"date": date,
}
db[project].insert_one(item)
```

데이터가 실제로 잘 들어갔는지 체크해보겠습니다. mongo 쉘에 접속하여 데이터를 확인해보세요.

```
$ mongo
> use projects
> db.circle.find()
```

#### 데이터 수정하기

```python
from pymongo import MongoClient
import datetime

client = MongoClient("192.168.219.105", 27017)
db = client.projects
project = "circle"
date = datetime.datetime.now().strftime("%Y-%m-%dT%H:%M:%S")
item = db[project].find_one({'name': "BAR_0010"})

item["text"] = "new text"
item["date"] = date
db[project].update_one({"name":"BAR_0010"}, {"$set": item}, upsert=False)
```

#### 데이터 가지고오기

```python
from pymongo import MongoClient

client = MongoClient("192.168.219.105", 27017)
db = client.projects
project = "circle"

item = db[project].find_one({'name': "BAR_0010"})
print(item["name"])
print(item["text"])
print(item["tags"])
print(item["date"])
```

#### 데이터 삭제하기

```python
from pymongo import MongoClient

client = MongoClient("192.168.219.105", 27017)
db = client.projects
project = "circle"

result = db[project].delete_many({"name": "BAR_0010"})
print(result)
```