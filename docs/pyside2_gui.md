# PySide2 알아보기. 프로그램 제작 예

중간에 테스트로 설치한 라이브러리로 인해서 PySide2 실행시 세그멘테이션 오류가 발생하여 이 부분을 잠시 뒤로 뺐습니다. (리눅스 설치후 pip와 PySide2부터 설치하면 잘 작동합니다. 충돌되는 부분을 찾게되면 기록하겠습니다.)

회사는 일반적으로 아래 성향을 띄는 툴을 자주 제작합니다.
- 파일관리 툴
- 라이브러리 툴
- 데이터 변환 툴
- 데이터 체크 툴
- 상태를 관찰하는 툴 : 프로젝트, 에셋, 인원, 진행률...
- 백업 툴
- 프로젝트 셋업툴
- 툴과 툴사이에 데이터를 전송하는 툴
- 자동설치 툴

취업을 목적으로 한다면 위 툴들을 테스트로 제작해보는 것을 추천합니다.
실무에 자주 사용되는 툴 패턴이기 때문입니다.

## Pyside 설치

```
$ pip install --user PySide2
```

## 예제파일
예제 파일을 파이썬으로 실행해보세요.

```bash
$ git clone https://github.com/PySide/pyside2-setup
$ cd examples
```

```
$ git clone https://github.com/pyside/pyside2-examples
```

## Reference
- pyside, pyqt를 사용하는 회사 : http://www.nukepedia.com/prepare-for-qt5
- 샷건이 사용하는 PySide2 형태를 볼 수 있는 사이트 : https://support.shotgunsoftware.com/hc/en-us/articles/219032858-Nuke?mobile_site=true
- David Emeny 블로그 : https://davemne.wordpress.com
- 프로젝트에 활용되는 GUI : https://benmorgananimation.wordpress.com/2017/09/13/making-a-picker-gui-for-maya-with-pyside-and-qtdesigner/
