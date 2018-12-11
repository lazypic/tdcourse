# OTIO
OTIO는 OpenTimelineIO의 약자입니다.
편집 Cut 정보를 다루는 API입니다. EDL파일이 너무 오래 되었기 때문에 EDL파일을 확장하기 위해 만들어진 포멧입니다. 픽사에서 만들어지고 있습니다. 파일포멧은 json 파일입니다.

EDL은 간단하지만 정보가 너무 최초이고,
AAF 포멧은 너무 많은 정보를 담고 있습니다.
OTIO는 중간정도의 입장에서 개발될 예정입니다.

결국 OTIO가 좋은점은 사용자 메타데이터를 넣을 수 있는 점이예요.
애니메이션 코코에서는 편집장비에서 EDL파일을 뽑아서 필요한 메타데이터를 넣고 OTIO를 만들어서 RV에서 리뷰했답니다.

## AAF란?
Advanced Authoring Format 의 약자입니다.
포스트프로덕션 환경에서 사용할 수 있는 프로페셔널 포멧입니다.
OTIO 프로젝트가 생겼을 만큼 AAF는 복잡합니다.

- https://en.wikipedia.org/wiki/Advanced_Authoring_Format
- http://aaf.sourceforge.net/docs/aafObjectModel.pdf

## OTIO의 목표
픽사에서의 최종 골은
파이널컷 프로, 아비드, 프리미어에서 OTIO를 뽑아서
샷건, RV, 마야에 그대로 활용하고
다빈치 리졸브, 언리얼, 유니티 엔진에 그대로 데이터를 활용하는 것을 목표로 하고 있습니다.

참고자료 : https://opentimelineio.readthedocs.io/en/latest/_static/OpenTimelineIO_2018_04_26_FMX_Published.key.pdf

참고자료를 보면 애니메이션 "CoCo" 작업에 사용된 자료구조를 같이 볼수 있습니다.

- 문서 : https://opentimelineio.readthedocs.io/en/latest/
- 소스코드 : http://opentimeline.io/


## 설치
pip를 이용해서 설치할 수 있습니다.

```
# pip install PySide2
# pip install opentimelineio
```

## 명령어
- otiocat
- otioconvert
- otiostat
- otioview
```
$ otioview path/to/your/file.edl
```