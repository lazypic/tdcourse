# 뉴크에서 Pyside2 사용하기

뉴크에서 GUI를 만드는 방법은 여러가지가 있습니다.
그중 PySide2를 활용하는 방법을 알아보겠습니다.

Hello World 띄우기
```python
from PySide2 import QtWidgets
label = QtWidgets.QLabel("hello World")
label.show()
```