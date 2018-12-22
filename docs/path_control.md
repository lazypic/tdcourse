# 파이썬으로 경로 추출하기
프로젝트 경로를 분리하는 방법을 다루어 보겠습니다.

```
/project/circle/shot/FOO/0010/comp/v001.nk
```

형태의 경로가 존재할 때 경로를 스플릿 하는방법을 다루겠습니다. 이 패턴은 경로 기반의 파이프라인 툴에서 자주 사용되는 패턴입니다.

회사에 가면 아래와 비슷한 경로를 다루게 됩니다. 아래 경로는 [lazypic](http://lazypic.org)에서 사용하는 경로를 참고하여 제작했습니다.

```
/project/circle/asset/char/mamma/model/v001.blend
/project/circle/asset/char/mamma/texture/v001.blend
/project/circle/asset/char/mamma/fur/v001.blend
/project/circle/asset/char/mamma/rig/v001.blend
/project/circle/asset/prop/stone/model/v001.blend

/project/circle/shot/FOO/0010/plate/v001/FOO_0010_plate_v001.####.exr
/project/circle/shot/FOO/0010/src/v001/FOO_0010_src_v001.####.exr
/project/circle/shot/FOO/0010/ref/v001/FOO_0010_ref_v001.####.exr

/project/circle/shot/FOO/0010/comp/v001.nk
/project/circle/shot/FOO/0010/comp/pub.nk
```

## 기본적인 경로 스플릿

```python
p = "/project/circle/shot/FOO/0010/comp/v001.nk"
plist = p.split("/")
print(plist)
```

```
['', 'project', 'circle', 'shot', 'FOO', '0010', 'comp', 'v001.nk']
```

## 패스와 파일명을 분리하는 패턴

```python
p = "/project/circle/shot/FOO/0010/comp/v001.nk"
path, filename = os.path.split(p)
print path
print filename
```

Output:
```
/project/circle/shot/FOO/0010/comp
v001.nk
```

## 파일명과 확장자를 가지고 오는 패턴

```python
p = "/project/circle/shot/FOO/0010/comp/v001.nk"
filename_with_ext = os.path.basename(p)
filename, ext = os.path.splitext(filename_with_ext)
print filename
print ext
```

Output:
```
v001
.nk
```