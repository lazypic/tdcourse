# 경로를 이용해서 Read노드 생성

뉴크에서 경로를 붙혀넣기 하면 자동으로 Read 노드가 생성됩니다.
이 특징을 위해서 라이브러리를 제작할 수 있습니다.

영상에 항상 로고같은 이미지를 넣어야하는 작업이 발생한다면,
로고를 생성하는 Read노드를 파이썬으로 만들 수 있습니다.
또는 로고를 생성하는 기즈모 형태로도 만들 수 있습니다.

```python
import nuke
read = nuke.nodes.Read(file="/path/logo.exr")
read["first"].setValue(start)
read["last"].setValue(end)
```

## 응용
- 프로젝트중 샷에 필요한 소스 이미지를 불러오는 자동화 스크립트
- URL_to_IN : 인터넷 소스를 다운받아서 in 폴더에 넣어주고 Read 노드를 생성시켜주는 스크립트 제작

## Reference
- https://fredrikaverpil.github.io/2016/05/23/nuke-script-read-node-from-write-node/