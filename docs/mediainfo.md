# MediaInfo
미디어 파일의 관련된 정보를 출력하는 프로그램입니다. 보통 코덱, 이미지 사이즈, 기타 메타데이터 정보등을 알아낼 때 사용합니다.

mediainfo를 테스트할 [샘플파일](sample.md)

## Commandline Tool
```
# yum install mediainfo
```

#### 사용법
굉장히 간단합니다. 명령어 이후 분석할 파일경로를 입력하면 됩니다.

```
$ mediainfo input.png
```

## PyMediaInfo
mediainfo은 파이썬 라이브러리로도 존재합니다.

pypi 홈페이지 : https://pypi.org/project/pymediainfo/

설치는 아래와 같습니다.

```
# pip install --upgrade setuptools
# pip install pymediainfo
```

파이썬을 이용하여 bit_rate, bit_rate_mode, codec을 가지고 오는 예제

example 리포지터리를 다운로드 받습니다. 이미 과거에 받았다면 이 단계는 넘겨도 좋습니다.
```
cd ~
git clone https://github.com/cgiseminar/examples
```

```python
import os
from pymediainfo import MediaInfo

media_info = MediaInfo.parse(os.getenv("HOME")+"/examples/movs/H264_1280x720_24fps.mov")
for track in media_info.tracks:
        if track.track_type == 'Video':
                print track.codec_id
                print track.duration #4125 / 4.125초 
                print track.frame_rate
                print track.width
                print track.height
```

아래와 같은 에러가 발생하면 mediainfo가 설치되어있지 않아서 그렇습니다.

```
OSError: dlopen(libmediainfo.so, 6): image not found
```