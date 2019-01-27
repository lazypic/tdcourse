# 뉴크에서 환경변수 체크하기

개발자가 선언한 환경변수가 잘 들어오는지 체크하기 위한 메시지 박스를 제작해 보겠습니다.

```python
from PySide2.QtWidgets import *
qmBox = QMessageBox(None)
qmBox.setText("$USER : %s" % (os.environ['USER']))
qmBox.show()
```