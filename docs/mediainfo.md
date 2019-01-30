# MediaInfo
미디어 파일의 관련된 정보를 출력하는 프로그램입니다. 보통 코덱, 이미지 사이즈, 기타 메타데이터 정보등을 알아낼 때 사용합니다.

mediainfo를 테스트할 [샘플파일](sample.md) 다운로드

## 설 치
mediainfo 는 yum 을 이용해서 설치가 가능합니다.
```bash
# yum install mediainfo
```

## 사용법
명령어 이후 분석할 파일경로를 입력하면 됩니다.

```
$ mediainfo input.png
$ mediainfo input.mov
```

## PyMediaInfo
mediainfo은 파이썬 라이브러리로도 존재합니다.

pypi 홈페이지 : https://pypi.org/project/pymediainfo/

설치는 아래와 같습니다.

```
# pip install --upgrade setuptools
# pip install pymediainfo
```

파이썬을 이용하여 bit_rate, bit_rate_mode, codec을 가지고 오는 예제를 작성해보겠습니다.

example 리포지터리를 다운로드 받습니다. 이미 과거에 진행했다면 이 단계는 넘겨도 좋습니다.
```bash
$ cd ~
$ git clone https://github.com/cgiseminar/examples
```


```python
#!/usr/bin/env python
import os
from pymediainfo import MediaInfo

media_info = MediaInfo.parse(os.getenv("HOME")+"/examples/movs/H264_1280x720_24fps.mov")
for track in media_info.tracks:
        if track.track_type == 'Video':
                print "codec", track.codec_id
                print "duration", track.duration #4209 / 4.209초 round(4.209 * 24)
                print "fps", track.frame_rate
                print "width", track.width
                print "height", track.height
                print "frames", int(round((float(track.duration) * float(track.frame_rate))/1000))
```
mov 정보가 잘 출력되는 확인해주세요.


> 참고 : 아래와 같은 에러가 발생하면 mediainfo가 설치되어있지 않아서 그렇습니다.

```bash
OSError: dlopen(libmediainfo.so, 6): image not found
```

## 실 습
- CentOS 설치 이후 mediainfo가 자동으로 설치되도록 자동 설치 스크립트에 기능을 추가합니다.
- CentOS 설치 이후 pip를 이용해서 pymediainfo 가 설치되도록 pip.sh 스크립트에 기능을 추가합니다.

## 응 용
- A 프로젝트에서는 아티스트에 의해 하루 수백개의 동영상이 생성됩니다. H.264 코덱으로 렌더링 하기로 약속했습니다. 규칙을 지키지 않은 mov를 찾는 스크립트를 고민해보세요.
- 서로 약속한 영상의 아웃풋 사이즈가 다를 때 경고를 주는 스크립트를 고민해보세요.