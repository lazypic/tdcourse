# 뉴크 메뉴 등록하기

뉴크 메뉴Bar에 매뉴를 추가하는 것은 간단합니다.
menu.py 파일에 Script > Hello Menu 라는 항목을 추가해 보겠습니다.

```python
import nuke
customMenus = menubar.addMenu("Script")
customMenus.addCommand("Hello Menu", "helloMenu()")

def helloMenu():
   nuke.message("hello Menu")
```


만약 함수를 다른 파일로 관리한다면, 아래처럼 작성도 가능합니다.

func.py
```python
import nuke
def helloMenu():
   nuke.message("hello Menu")
```

menu.py
```python
import nuke
import func

customMenus = menubar.addMenu("Script")
customMenus.addCommand("Hello Menu", "func.helloMenu()")

```