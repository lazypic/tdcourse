# 퍼포먼스 기능 체크

뉴크는 수많은 소스를 불러서 합성하는 툴입니다.
많은 소스를 로딩하기 때문에 무거운 샷 작업시 서버에 굉장히 많은 I/O 부하를 주게됩니다.
회사에 아티스트가 늘어나면 늘어날수록 그 부하는 굉장해집니다.

뉴크 작업 노드가 굉장히 거대해지면 어디 지점에서 부하가 발생하는 알고 싶습니다.
뉴크는 이미 그 기능이 내장되어있습니다.
여러분의 노드가 점점 무거워지는데 어느 부분을 최적화 해야할 지 잘 모르겠다면 아래 기능을 활용해보세요.

```python
import nuke
nuke.startPerformanceTimers()
nuke.stopPerformanceTimers()
```

위 명령어를 뉴크 Python 스크립트창에서 타이핑해보세요.

노드가 거대하면 자주 사용하게 될 기능이니 메뉴에 등록해보겠습니다.

menu.py
```
mb = menubar.addMenu("Lazypic")
mb.addCommand("StartPerformanceTimers", "nuke.startPerformanceTimers()")
mb.addCommand("StopPerformanceTimers", "nuke.stopPerformanceTimers()")
```

## Reference
- https://learn.foundry.com/nuke/developers/90/pythondevguide/performance.html