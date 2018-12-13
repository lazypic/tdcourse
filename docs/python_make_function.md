# 파이썬 함수 만들기
회사에서 대부분 업무는 함수단위 또는 클래스 단위의 프로그래밍 업무를 자주 접하게 됩니다.
오늘은 간단한 함수를 하나 만들어 보겠습니다.

아마도 모든 회사에서 가장 많이 사용하는 함수는 회사에서 진행중인 프로젝트 리스트를 가지고 오는 방법일 것입니다.
회사마다 다르겠지만 일반적으로 2가지 경우가 존재합니다.
- 폴더에서 프로젝트를 가지고 오는 방법
- DB에서 프로젝트를 가지고 오는 방법

대부분의 모든 회사는 프로젝트 목록을 가지고 오는 함수 하나쯤은 내부에 작성되어 있을 확률이 높습니다.
회사에서 /shows 폴더 내부에서 모든 프로젝트가 진행된다고 가정을 하고 프로젝트 리스트를 가지고 오는 함수를 제작해보겠습니다.

먼저 / 경로에 shows 폴더를 제작해보겠습니다. 또한 내부에 circle 이라고 하는 프로젝트 폴더를 생성하겠습니다.
```bash
$ su
# cd /
# mkdir shows
# chmod 775 shows
# chown root:$USER shows
# exit
$ cd shows
$ mkdir circle
```

프로젝트 리스트를 가지고 오는 함수를 짜는 것은 간단합니다.
```python
#coding:utf8
import os

def Projects():
    """
    Projects 함수는 프로젝트 목록을 리스트로 반환한다.
    """
    return os.listdir("/shows")

if __name__ == '__main__':
    print(Projects())
```

하지만 위 함수에는 단점이 있습니다. 폴더가 아닌 파일까지 전부 프로젝트로 인식한다는 점입니다. 폴더만 프로젝트로 인식하기 위해서는 아래처럼 예외처리가 필요합니다.

```python
#coding:utf8
import os

def Projects():
    """
    Projects 함수는 프로젝트 목록을 리스트로 반환한다.
    """
    plist = []
    for i in os.listdir("/shows"):
        if not os.path.isdir("/shows/"+i):
            continue
        plist.append(i)
    return plist

if __name__ == '__main__':
    print(Projects())
```

우리는 간단하게 프로젝트 경로를 가지고 오는 함수를 제작했습니다.
이런식으로 회사에 존재하는 수많은 서버, OS에 따라서 프로젝트를 가지고 오는 방법은 서로 조금씩 다르겠지만 컨셉은 비슷합니다.
