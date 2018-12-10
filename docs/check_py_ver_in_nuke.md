# 뉴크 내부 Python버전 체크 / OS체크

프로그래밍을 하다 보면 뉴크버전, 뉴크내부 파이썬 버전, 뉴크 내부 라이브러리 버전 확인을 하며 프로그래밍 해야할 때가 있습니다. 회사는 다양한 OS(linux, windows, macOS)에서 코드를 돌리기 때문에 특정코드는 OS체크에 따라 코드가 분기될 때도 있습니다.

뉴크 내부 파이썬 버전, 라이브러리 버전, OS에 따른 코드 분기방법을 다루겠습니다.

## OS체크

OS에 따른 코드 분기

```python
import sys
if sys.platform == "linux2":
    print("linux")
elif sys.platform == "win32":
    print("windows")
elif sys.platform == "darwin":
    print("macOS")
else:
    print("unknown")
```

## 뉴크 버전
뉴크의 버전을 알아내는 방법은 아래와 같습니다.

```python
import nuke
print(nuke.env["NukeVersionString"])
```

회사에서 일하게 되면 뉴크 버전마다 간혹 코드를 분기해야하 하는 상황이 발생합니다.
아래 형태로 활용이 가능합니다.

```python
import nuke
ver = nuke.env["NukeVersionString"]
if ver.startswidth("11."):
    print("Nuke11.x")
else:
    print("not Nuke11.x")
```

## 뉴크 내부 Python 버전확인
```python
import sys
print(sys.version)
print(sys.version_info)
```


파이썬 2.7.9 버전보다 낮으면 경고를 주는 문장을 출력하는 예제입니다.
```python
#coding:utf8
import sys
if sys.version_info < (2,7,9): # vfx reference platform 2019
    print("not requirements Vfx Reference Platform.")
```

## 뉴크 내부 Pyside2 버전확인
뉴크 Script Editor에서 PySide2 버전을 체크해보세요.

```python
import PySide2
print(PySide2.__version__)
```

## Reference
- https://davemne.wordpress.com/2017/08/07/nuke-11-and-pyside2/