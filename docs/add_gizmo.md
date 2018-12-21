# Python을 이용해서 기즈모 등록하기

기즈모를 등록하는 방법은 간단합니다. NUKE_PATH 환경변수에 init.py, menu.py를 수정해주면 됩니다.

위에서 우리가 만든 slate.gizmo, timecode 기즈모를 $NUKE_PATH/gizmo 경로에 넣어주세요.

init.py
```python
import nuke
nuke.pluginAddPath("./gizmo", addToSysPath=True)
```

menu.py
```python
tb = nuke.toolbar("Nodes")
m = tb.addMenu("Lazypic", icon="lazypic_logo.png")
m.addMenu("Draw")
m.addCommand("Draw/Slate", "nuke.createNode('slate')")
m.addCommand("Draw/Timecode", "nuke.createNode('timecode')")
```

저는 기즈모에 접근할 뉴크 툴바 메뉴를 만들 때 제 소속인 Lazypic 이라는 이름을 사용했습니다.

뉴크를 띄워서 노드그래프 창에서 Tab을 누르고 우리가 만든 기즈모 이름을 타이핑해서 기즈모가 잘 생성되는지 체크하세요.