# 뉴크에서 환경변수 체크하기

개발자가 선언한 환경변수가 잘 들어오는지 체크하기 위한 메시지 박스를 제작해 보겠습니다.

```python
from PySide2.QtWidgets import *
qmBox = QMessageBox(None)
qmBox.setText("$USER : %s" % (os.environ['USER']))
qmBox.show()
```

## 실습
- 아래 항목에 대한 환경변수를 체크해보세요.
    - OCIO
    - NUKE_PATH
    - NUKE_FONT_PATH
    - USER
    - 앞으로 사용하게될 환경변수들...