# 파이썬에서 인수처리
파이썬 코드에서는 sys.argv 값을 이용해서 사용자가 입력한 인수를 출력할 수 있습니다.

test.py
```python
import sys
print(sys.argv)
```


```bash
$ python test.py 1 2 3 4 5 6 7
['test.py', '1', '2', '3', '4', '5', '6', '7']
```

이 형태를 그대로 활용하여 프로그램을 만들 수 있지만 디테일한 인수를 설정, 유지보수, 인수관리를 위해서는 인수를 잘 처리할 수 있는 라이브러리 사용을 권장합니다.

파이썬에는 인수처리를 위한 argparse가 내장되어있습니다.
이번 시간에는 argparse 라이브러리를 사용하는 방법을 알아보겠습니다.

Project, Shot, User, Task를 입력받아 간단하게 출력할 info.py 프로그램을 작성하겠습니다.

info.py
```python
#!/usr/bin/env python
#coding:utf8
import argparse

# 도움말 출력시 머릿말과 꼬릿말 설정
parser = argparse.ArgumentParser(description='info 프로그램은 project, shot, user, task 정보를 입력받아서 출력합니다.', epilog="© 2018. lazypic. all rights reserved"))

#인수설정
parser.add_argument("-p", "--project", help="project name")
parser.add_argument("-s", "--shot", help="shot name")
parser.add_argument("-u", "--user", help="user name")
parser.add_argument("-t", "--task", help="task name")

#인수파싱
args = parser.parse_args()

#인수출력
print(args.project)
print(args.shot)
print(args.user)
print(args.task)
```

터미널에서 도움말 출력
```bash
$ python info.py -h
```

터미널에서 인수 테스트
```bash
$ python info.py -p circle -t comp -u woong -s FOO_0010
```

우리가 만든 파이썬 스크립트가 리눅스명령어와 비슷하게 인수를 처리하도록 만들어봤습니다. 이제 우리 스크립트는 리눅스의 명령어들과 조금씩 닮아가고 있습니다.

사용자에게 받는 인수는 프로그램 내부의 자료구조와 굉장히 밀접하게 관련되어 있습니다.
인수를 처리할 때는 직접 sys.argv를 파서하기 보다는 위에 작성했던 argparse 라이브러리를 사용하는 것이 앞으로 스크립트를 제작하며 확장해나가기 좋습니다.

## Reference
- https://docs.python.org/2/library/argparse.html