# 뉴크셋팅

뉴크를 설치하고 추가 기능들을 개발하기 위한 첫 단계입니다.
기업, 조직에서 가장 큰 자산이 되는 것을 에셋이라고 하고 에셋을 잘 관리할 수 있는 환경을 1차적으로 만들 필요가 있습니다.

뉴크에서는 보통 아래 설명된 데이터를 에셋으로 분류하며, 기업은 항상 이 데이터를 축적하려고 노력합니다.

- 재활용가능한 노드 : .nk
- Python코드 : .py
- 프로젝트를 매끄럽게 진행해줄 Gizmo : .gizmo
- 회사 로고 같은 이미지 : .png, .jpg, .exr
- 프로젝트에 사용되는 Fonts : .otf, .ttf
- 프로젝트와 관련된 LUT : .cube, .3dl, .cc
- C++로 만든 플러그인 데이터 : .so
- 재사용 가능한 다양한 소스들

위 데이터를 각 폴더로 구분하여 뉴크가 실행될 때 각 에셋들이 잘 로딩되면 매우 편할 것 입니다.
각 데이터에 해당하는 폴더를 뉴크셋팅 폴더 하위에 만들어 봅시다.

우리가 만들 폴더는 아래와 같습니다.

- lib : 컴파일된 C++ 데이터
- scripts : Python, Tcl 스크립트
- gizmos : 뉴크 기즈모
- images : 이미지 에셋
- luts : LUT파일
- font : 폰트데이터
- nk : 재활용 가능한 뉴크파일

위 예는 The Foundry 뉴크를 기준으로 리스트를 작성했지만,
다른 툴들도 개념은 굉장히 비슷합니다.

뉴크셋팅 경로는 홈디렉톨에 nuke라는 폴더를 만들고 제작해보겠습니다.
```
$ cd ~
$ cd nuke
```

위 에셋들중에서 scripts, gizmos, lib, images 에셋은 Plugin이기 때문에 플러그인 패스에 추가합니다.
추가하면 menu.py에서 해당경로의 리소스를 사용할 수 있게 됩니다.

init.py에 아래 줄을 추가해주세요.
```
import nuke
nuke.pluginAppendPath("./gizmos")
nuke.pluginAppendPath("./images")
nuke.pluginAppendPath("./lib")
nuke.pluginAppendPath("./scripts")
```

## 폰트
font도 좋은 에셋이 됩니다. 폰트의 경우 뉴크에서는 `NUKE_FONT_PATH` 환경변수를 잡아서 사용합니다.

.bashrc
```
export NUKE_PATH="$HOME/nuke"
export NUKE_FONT_PATH="$NUKE_PATH/font"
```

font폴더에 폰트를 넣으면 뉴크에서 사용가능한 상태가 됩니다.
폰트를 사용할 때는 항상 라이센스 정책을 확인하시고 사용하세요.

## Reference
- https://www.programcreek.com/python/example/91909/nuke.pluginAddPath
- https://learn.foundry.com/nuke/8.0/content/user_guide/configuring_nuke/nuke_environment_variables.html
