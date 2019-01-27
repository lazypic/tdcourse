# Write노드 생성 스크립트

파이프라인 상에서 모든 툴의 Input, Output은 중요합니다.
Write노드는 뉴크 툴에서 Output 기능을 담당합니다.
Write노드와 관련된 파이썬 스크립트를 작성해보겠습니다.

## 실습1 : 파이썬을 이용해서 Write노드 만들기
- 우리가 필요한 아웃풋 폴더를 자동으로 생성할 수 있도록 설정해봅시다.
    - 현재 열여있는 뉴크 파일을 기준으로 output폴더를 만들고 파일명을 기준으로 제작합니다.

- 필요한 파일명, 컬러스페이스가 자동으로 설정될 수 있도록 해봅시다.

중요한 기능이 되는 노드는 아래와 같습니다. $NUKE_PATH/script 경로에 저장해주세요.

writenode.py
```python
import nuke
tail = nuke.selectedNode()
w = nuke.nodes.Write()
w["file_type"].setValue("exr")
w["colorspace"].setValue("linear")
w["file"].setValue("/test/test.####.exr")
w.setInput(0, tail)
```

## 실습2 : Write 하기전 Reformat 붙히기

```python
tail = nuke.selectedNode()
r = nuke.nodes.Reformat()
r["type"].setValue("to box")
r["box_width"].setValue("1920")
r["box_height"].setValue("1080")
r["box_fixed"].setValue("true")
r.setInput(0, tail)
```


## 실습3 : 이전에 제작된 슬레이트 기즈모를 불러오기

코드의 기본형
```python
tail = nuke.selectedNode()
slate = nuke.nodes.slate()
slate.setInput(0, tail)
```

## 실습4 : 시작 타임코드 설정

코드의 기본형
```python
import nuke
tail = nuke.selectedNode()
m = nuke.nodes.AddTimeCode()
m["startcode"].setValue("01:00:00:00")
m["useFrame"].setValue("true")
m["frame"].setValue(1001)
m.setInput(0, tail)
```

## GUI테스트

```python
from PySide2.QtWidgets import *

class GenWrite(QWidget):
    reformatSize = "2048x1152"
    def __init__(self):
        super(GenWrite, self).__init__()
        self.ok = QPushButton("OK")
        self.cancel = QPushButton("Cancel")
        self.cb = QComboBox()
        self.cb.addItem("2048x1152")
        self.cb.addItem("1920x1080")
        self.cb.addItem("2048x872")
        self.reformat = QCheckBox("&reformat", self)
        self.reformat.setChecked(True)
        self.proxy = QCheckBox("&proxy", self)
        self.proxy.setChecked(True)
        self.slate = QCheckBox("&slate", self)
        self.slate.setChecked(True)
        #event
        self.ok.clicked.connect(self.bt_ok)
        self.cb.currentIndexChanged.connect(self.indexChanged)
        self.cancel.clicked.connect(self.close)
        # set layout
        layout = QGridLayout()
        layout.addWidget(self.reformat, 0, 0)
        layout.addWidget(self.cb, 0, 1)
        layout.addWidget(self.proxy, 1, 0)
        layout.addWidget(self.slate, 1, 1)
        layout.addWidget(self.cancel, 2, 0)
        layout.addWidget(self.ok, 2, 1)
        self.setLayout(layout)

    def indexChanged(self):
        self.reformatSize = self.cb.currentText()

    def bt_ok(self):
        print "reformatSize %s" % (self.reformatSize)
        print self.reformat.isChecked()
        print self.proxy.isChecked()
        print self.slate.isChecked()
        self.close()

global customApp
try:
    customApp.close()
except:
    pass
customApp = GenWrite()
try:
    customApp.show()
except:
    pass
```

## 응용
위 코드 패턴을 이용하면 굉장히 정형화된 합성작업들은 회사내부에서 자동화를 만들 수 있습니다.