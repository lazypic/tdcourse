# 테스트 코드

실무 작업을 할 때는 함수를 작성하고 꼭 필요한 함수에 대해서는 테스트 코드를 작성하는 것이 좋습니다. 버그를 미연에 방지하고 PR시 다른 개발자들이 추가 기능에 대해서 안심도 하는 역할을 합니다.

### Python 테스트 코드 작성
아래 두 값을 더하는 함수가 있습니다.
만약 숫자만 더해야 한다고 할 때, 어떻게 테스트 코드를 작성하는 지 알아보겠습니다.

```python
# runcode.py
def addNum(a,b):
    return a + b
```

테스트 코드는 아래처럼 작성합니다.

```python
# testcode.py
import unittest
from runcode import *
class Test_code(unittest.TestCase):
    def test_addNum(self):
        self.assertEqual(addNum(1,2), 3) # 예측값을 적습니다.
        self.assertEqual(addNum(0.1,2), 2.1)

if __name__ == "__main__":
    unittest.main()
```

Test 코드는 터미널에서 아래처럼 실행합니다.
```
$ python testcode.py
```

이번에는 테스트 코드에 숫자대신 문자를 하나 넣어보죠.

```python
# testcode.py
import unittest
from runcode import *
class Test_code(unittest.TestCase):
    def test_addNum(self):
        self.assertEqual(addNum(1,2), 3)
        self.assertEqual(addNum(0.1,2), 2.1)
        self.assertEqual(addNum("테",2), 2)

if __name__ == "__main__":
    unittest.main()
```

테스트 코드를 실행하면 아래와 같은 메시지가 출력됩니다.
문자를 넣는것을 우리는 예상하지 못하고 함수를 짰기 때문입니다.
```
======================================================================
ERROR: test_addNum (__main__.Test_code)
----------------------------------------------------------------------
Traceback (most recent call last):
  File "testcode.py", line 9, in test_addNum
    self.assertEqual(addNum("테",2), 2)
  File "/Users/woong/test/runcode.py", line 7, in addNum
    return a+b
TypeError: cannot concatenate 'str' and 'int' objects

----------------------------------------------------------------------
Ran 1 test in 0.000s

FAILED (errors=1)
```

일반적으로 위 코드는 문제가 있습니다. a값에 숫자가 올지, 문자가 올지 알 수 없기 때문이죠. a 또는 b 값중 하나에 문자가 들어가면 아래와 같은 타입에러가 발생할 것 입니다.

```
TypeError: cannot concatenate 'str' and 'int' objects
```

실무에서는 addNum 함수 하나를 작성하더라도 모든 에러를 생각하며 작성할 필요가 있습니다.
강력하게 타입을 체크해야하는 상황이라면 아래같은 코드를 작성해야 할 필요가 있습니다.
편의상 두 값을 더할 수 없다면 0을 반환하도록 했습니다.

```python
# coding:utf-8
# runcode.py
def addNum(a,b):
    """
    addNum 함수는 두 수를 더하는 함수 입니다.
    """
    if not(isinstance(a,int) or isinstance(a,float)):
        return 0, "두 값을 더할 수 없습니다."
    if not(isinstance(b,int) or isinstance(b,float)):
        return 0, "두 값을 더할 수 없습니다."
    return a+b, None
```


이 함수에 문제가 있는지 없는지를 판단하기 위하여 a 또는 b 값에 int, float 타입이 아닌 다른 type을 넣어서 테스트해 봅시다.
관련 테스트 코드는 아래와 같은 구조를 띄게 됩니다.

```python
# coding:utf-8
# testcode.py
import unittest
from runcode import *
class Test_code(unittest.TestCase):
    def test_addNum(self):
        self.assertEqual(addNum(1,2), (3,None))
        self.assertEqual(addNum(0.1,2), (2.1,None))
        self.assertEqual(addNum("테",2), (0,"두 값을 더할 수 없습니다."))
        self.assertEqual(addNum("테","스"), (0,"두 값을 더할 수 없습니다."))
        self.assertEqual(addNum([1,2],[1,2]), (0,"두 값을 더할 수 없습니다.")) # 리스트를 넣었습니다.
        self.assertEqual(addNum({"a":1},(1)), (0,"두 값을 더할 수 없습니다.")) # 딕셔너리와 튜플을 더해보겠습니다.
if __name__ == "__main__":
    unittest.main()
```

테스트가 잘 진행되면 아래와 같은 메시지를 출력합니다.

```
$ python testcode.py
.
---------------------------------------------------------------
Ran 1 test in 0.000s

OK
```

이상으로 파이썬으로 테스트 코드를 작성하는 과정을 알아보았습니다.