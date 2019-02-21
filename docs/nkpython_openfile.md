# Read 노드와 관련된 스크립트

## 폴더열기
Read 또는 Write 노드를 선택하고 단축키를 누르면 해당 소스의 폴더를 오픈하는 스크립트를 제작해 보겠습니다.
굉장히 편리한 기능이라서 많은 회사들이 작성해서 사용하고 있습니다.

아래는 우리가 작성하는 코드에서 중요하게 사용되는 함수입니다.

```python
import os
import nuke
import nukescripts

node = nuke.selectedNode()
path = node["file"].value()
nukescripts.start(os.path.dirname(path))
```

본격적으로 코드를 작성하기 전에 위 간단한 코드로 기능 테스트를 진행하겠습니다.
진행은 뉴크 Python 창에서 실습해보겠습니다.


아래 파일을 $NUKE_PATH/scripts 경로에 생성해주세요.

openfile.py
```python

import nukescripts

def openfile():
    # 이 부분은 실습을 통해서 같이 작성해봅니다.
```

menu.py
```python
import nuke
import openpath

mb = menubar.addMenu("Lazypic")
mb.addCommand("OpenFile", "openfile.openfile()", "F8")
```

생각해야할 점
- 만약 여러개의 노드를 사용자가 선택후 위 기능을 실행한다면 어떻게 처리됩니까?
- 경로가 존재하지 않으면 어떻게 처리하겠습니까?
- file 이라는 옵션을 사용하는 다른 노드들도 기능이 지원되도록 작성해보세요.


#### Reference
- https://support.foundry.com/hc/en-us/articles/208720909-Q100118-Setting-custom-keyboard-shortcuts-in-Nuke-9-and-10

## 실습
- 여러분이 작성한 함수 리펙토링
- github 업로드, 코드리뷰
