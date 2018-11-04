# MediaInfo

[샘플파일](sample.md)
### Commandline Tool
```
# yum install mediainfo
```

### PyMediaInfo
```
# pip install MediaInfo
```

파이썬 예제
```
from MediaInfo import MediaInfo

info     = Mediainfo(filename = '/media/test.ts')
infoData = info.getInfo()

info     = Mediainfo(filename = '/media/test.ts', cmd = '/usr/bin/ffprobe')
infoData = info.getInfo()

info     = Mediainfo(filename = '/media/test.ts', cmd = '/usr/bin/mediainfo')
infoData = info.getInfo()
```

