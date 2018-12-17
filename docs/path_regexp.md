# 레귤러 익스프레션을 사용하여 경로 추출하기

일반적인 경로 분리방법은 실제로 잘 사용하지 않습니다.
프로젝트 중간에 경로가 추가될 수도 있고 규칙이 바뀔 수 있기 때문입니다.
그래서 실제 경로에서 데이터를 불러올 때 레귤러 익스프레션을 선호하기도 합니다.
다른 개발자들이 안심할 수 있도록 테스트 코드를 작성해두면 더 신뢰받는 함수가 되겠죠.

```
/show/circle/shot/FOO/0010/comp/v001.nk
```

예전과 다른 방식으로 프로젝트를 가지고 오는 함수를 짜보겠습니다.
이번엔 레귤러 익스프레션을 사용합니다.

레귤러 익스프레션 실습페이지 링크 : 

실제 실무에서는 프로젝트를 가지고 오기 위해서 아래와 같은 코드를 작성합니다. 더 확실하게 프로젝트를 가지고 올 수 있습니다.

pathapi.py
```python
#!/usr/bin/env python
#coding:utf
import sys
import re

path = "/show/circle/shot/FOO/0010/comp/v001.nk"

def project(path):
    p = re.findall('/show/(\S[^/]+)', path)
    if len(show) == 1:
        return p[0], None
    return "", "project 정보를 경로에서 가지고 올 수 없습니다."

if __name__ == "__main__":
    project, err = project(path)
    if err:
        sys.stderr.write(err+"\n")
        exit(1)
    print project
```
- `\S` 를 사용한 이유는 공백이 없는 유니코드가 프로젝트이름 조건과 같기 때문입니다.
- `[^/]` 가 붙어있는 이유는 `/show/circle/` 형태로 입력을 받을 때 맨 뒤 `/`를 제거하기 위함 입니다. `[ ]` 문자 내부에 `^`문자를 사용하면 예외시키라는 뜻이 있습니다.

testcode.py
```python
#!/usr/bin/env python
#coding:utf8
import unittest
from pathapi import *

class Test_path(unittest.TestCase):
    def test_project(self):
        이곳부터 추가하기
```


## 실습
- seq, shot, task를 가지고 오는 레귤러 익스프레션 작성하기
- 테스트코드 작성하기.

## Reference
- https://docs.python.org/2/library/re.html