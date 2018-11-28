# MediaInfo
미디어 파일의 관련된 정보를 볼 수 있는 프로그램입니다. 보통 코덱, 이미지 사이즈, 기타 메타데이터 정보등을 알아낼 때 사용합니다.

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

```
from pymediainfo import MediaInfo
media_info = MediaInfo.parse('test.mov')
for track in media_info.tracks:
    if track.track_type == 'Video':
        print track.bit_rate, track.bit_rate_mode, track.codec
```

