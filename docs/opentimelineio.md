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
- otiocat : otio파일을 STDOUT으로 출력합니다.
- otioconvert
```
 env OTIO_PLUGIN_MANIFEST_PATH=mymanifest.otio.json:$OTIO_PLUGIN_MANIFEST_PATH bin/otioconvert -i somefile.edl --media-linker="awesome_studios_media_linker" -o /var/tmp/test.otio
```

```
python otioconvert.py -i /mnt/Entretenimento/Temp/sandro/R01_BASE_Reference_v2.edl -o /mnt/Entretenimento/Temp/sandro/R01_BASE_Reference_v2.rv
```

- otiostat : otio 파일의 유효성 검사, 통계를 출력합니다.

아래서처럼 파일에 이상이 있는지 체크할 수 있습니다.

```
$ otiostat test.edl
```

파일에 이상이 있다면 무엇이 이상한지 출력해줍니다.
파일에 존재하면 안되는 수치가 있다면 출력해줍니다.
아래는 에러내용중 하나입니다.

Error
```
The file did not successfully parse, with error: Source and record duration don't match: RationalTime(260, 24.0) != RationalTime(284, 24.0) for clip Test rename
```

- otioview
![otioview](https://user-images.githubusercontent.com/3489076/44323186-a54ed980-a405-11e8-8c65-28999d6c244f.png)

    사용법
    ```
    $ otioview path/to/your/file.edl
    ```