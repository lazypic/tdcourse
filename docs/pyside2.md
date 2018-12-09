# PySide2
먼저 [pip](pip.md)를 설치합니다.

### 설치
```
# pip install PySide2
```

잘 작동된다면 아래 코드를 타이핑후 실행해보세요.

pyside2_test.py

```
import sys
from PySide2 import QtWidgets


app = QtWidgets.QApplication(sys.argv)

hello = QtWidgets.QPushButton("Hello PySide2")
hello.resize(100, 30)

hello.show()

sys.exit(app.exec_())
```

```
$ python pyside2_test.py
```