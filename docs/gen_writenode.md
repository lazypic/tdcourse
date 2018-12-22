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

## 응용
위 코드 패턴을 이용하면 굉장히 정형화된 합성작업들은 회사내부에서 자동화를 만들 수 있습니다.