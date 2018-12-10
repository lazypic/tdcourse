# 파이썬에서 인수처리
파이썬 스크립트에서 sys.argv 값을 이용해서 터미널에서 전달받은 인수를 출력할 수 있습니다.

```python
import sys
print(sys.argv)
```

이 형태를 활용하여 프로그램을 만들 수 있지만 디테일한 인수를 설정, 관리하기 위해서는 인수를 처리하는 라이브러리를 사용하기를 권장합니다.

파이썬에는 인수처리를 위한 argparse가 내장되어있습니다.

Project, Shot, User, Task를 입력받아 간단하게 출력할 info.py 프로그램을 제작해 보겠습니다.

초기화
```python
#!/usr/bin/env python
#coding:utf8
import argparse

parser = argparse.ArgumentParser(description='info 프로그램은 project, shot, user, task 정보를 입력받아서 출력합니다.', epilog="© 2018. lazypic. all rights reserved"))
```

인수추가하기
```python
parser.add_argument("-p", "--project", help="project name")
parser.add_argument("-s", "--shot", help="shot name")
parser.add_argument("-u", "--user", help="user name")
parser.add_argument("-t", "--task", help="task name")
```

인수 파싱하기
```python
args = parser.parse_args()
```

인수 출력하기
```python
print(args.project)
print(args.shot)
print(args.user)
print(args.task)
```

도움말 출력
```
$ python info.py -h
```

테스트 입력

```
$ python info.py -p circle -t comp -u woong -s FOO_0010
```

우리가 만든 파이썬 스크립트가 리눅스명령어와 비슷하게 인수를 처리하도록 만들어봤습니다.

사용자에게 받는 인수는 프로그램 내부의 자료구조와 굉장히 밀접하게 관련되어 있습니다.
때문에 인수를 처리할 때는 직접 sys.argv를 파서하기 보다는 위에 작성했던 argparse 라이브러리를 사용하는 것이 스크립트를 제작하며 확장해나가기 좋습니다.

## Reference
- https://docs.python.org/2/library/argparse.html