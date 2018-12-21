# Read 노드와 관련된 스크립트

## 폴더열기
Read 또는 Write 노드를 선택하고 단축키를 누르면 해당 소스의 폴더를 오픈하는 스크립트를 제작해 보겠습니다. 굉장히 편리한 기능이라서 많은 회사들이 작성해서 사용하고 있습니다.


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

## ffmpeg를 활용한 mov 생성
일반적으로 렌더팜을 이용해서 mov를 생성하지만 저희는 렌더팜 환경이 아니기 때문에 FFmpeg를 이용해서 mov를 생성하는 코드를 작성해보겠습니다.

- ref : http://www.nukepedia.com/gizmos/image/ffmpeg_write

## proxy 이미지 생성
