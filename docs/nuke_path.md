# Nuke Path
nukeset리포지터리를 생성, 적용하는 방법을 알아봅니다.

~/centos/env/init.env
```
export NUKE_PATH=$HOME/app/nukeset
```

## 설정파일을 불러오는 순서
1. 뉴크가 설치된 경로
1. NUKE_PATH
1. ~/.nuke

그룹 셋팅이후 사용자가 추가적으로 셋팅을 하고 싶다면 .nuke 폴더를 활용해달라고 하면됩니다.
