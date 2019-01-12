# 뉴크에서 Pyside2 사용하기

뉴크에서 GUI를 만드는 방법은 여러가지가 있습니다.
그중 PySide2를 활용하는 방법을 알아보겠습니다.

간단하게 Hello World 띄우기
```python
from PySide2 import QtWidgets
label = QtWidgets.QLabel("hello World")
label.show()
```

레이아웃을 만들어서 라벨 넣기
```python
from PySide2.QtWidgets import *

w = QWidget()
lb = QLabel()
lb.setText("Hello World")
layout = QHBoxLayout()
layout.addWidget(lb)
w.setLayout(layout)
w.show()
```

레이아웃1
```python
from PySide2.QtWidgets import *

window = QWidget()
button1 = QPushButton("One")
button2 = QPushButton("Two")
button3 = QPushButton("Three")
button4 = QPushButton("Four")
button5 = QPushButton("Five")

layout = QHBoxLayout()
layout.addWidget(button1)
layout.addWidget(button2)
layout.addWidget(button3)
layout.addWidget(button4)
layout.addWidget(button5)

window.setLayout(layout)
window.show()
```

레이아웃2
```python
from PySide2.QtWidgets import *

window =  QWidget()
button1 =  QPushButton("One")
button2 =  QPushButton("Two")
button3 =  QPushButton("Three")
button4 =  QPushButton("Four")
button5 =  QPushButton("Five")

layout =  QGridLayout()

layout.addWidget(button1, 0, 0)
layout.addWidget(button2, 0, 1)
layout.addWidget(button3, 1, 0, 1, 2)
layout.addWidget(button4, 2, 0)
layout.addWidget(button5, 2, 1)

window.setLayout(layout)
window.show()
```

## 실습1
버튼을 2개 만들고 실제 작동되는 기능을 제작해보자.

- 리눅스 경로를 윈도우즈 경로로 변경하기.
```
/project/ -> //10.20.30.40/project/
```

- 윈도우즈 경로를 리눅스 경로로 변경하기.
```
//10.20.30.40/project/ -> /project/
```