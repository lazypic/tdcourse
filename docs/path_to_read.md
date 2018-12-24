# 경로를 이용해서 Read노드 생성

뉴크에서 경로를 붙혀넣기 하면 자동으로 Read 노드가 생성됩니다.
이 특징을 위해서 라이브러리를 제작할 수 있습니다.

영상에 자주 로고를 넣어야하는 작업이 발생한다면,
로고를 생성하는 Read노드를 파이썬으로 만들 수 있습니다.
또는 로고를 생성하는 기즈모를 만들 수 있습니다.

```python
import nuke
read = nuke.nodes.Read(file="path")
read["first"].setValue(start)
read["last"].setValue(end)
```

## Reference
- https://fredrikaverpil.github.io/2016/05/23/nuke-script-read-node-from-write-node/