# 뉴크 View LUT 설정
View LUT를 추가히기 위해서는 init.py를 수정해야 합니다.
앞서 사용했던 `AlexaV3_K1S1_LogC2Video_Rec709_EE_nuke3d.cube` LUT를 뉴크 Viewer에 등록해보겠습니다.

이 실습을 따라하기 위해서는 NUKE_PATH 환경변수가 잡힌 경로의 luts폴더에 `AlexaV3_K1S1_LogC2Video_Rec709_EE_nuke3d.cube` 파일을 넣어주어야 합니다.

참고 : 뉴크의 Vectorfield 노드는 LUT를 이미지에 적용하는 노드입니다.

init.py
```python
import os
import nuke

nukePath = os.environ['NUKE_PATH']
nuke.ViewerProcess.register("AlexaV3LogC", nuke.createNode, ( "Vectorfield", "vfield_file %s/luts/AlexaV3_K1S1_LogC2Video_Rec709_EE_nuke3d.cube colorspaceIn AlexaV3LogC" % (nukePath)))
```

## 실습
- 다른 카메라의 LUT도 등록해보세요.
- 직접 LUT를 만들고 등록해보세요.
