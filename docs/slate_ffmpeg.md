# FFmpeg를 이용한 슬레이트 제작
FFmpeg를 이용해서 슬레이트를 제작할 수 있습니다.

일반적으로 뉴크 기즈모를 이용해서 슬레이트를 많이 처리합니다.
ffmpeg로 제작하면 라이센스 비용이 들지 않습니다.

![ffmpeg_slate](../figures/ffmpeg_slate01.png)

```
ffmpeg -f image2 -start_number 100 -r 24 -i ~/examples/FOO_0010/FOO_0010.%4d.jpg  -vcodec libx264 -vf "drawbox=x=0:y=0:w=iw:h=50:color=black@0.3:width=iw:height=50:t=50","drawbox=x=0:y=ih-50:w=iw:h=ih:color=black@0.3:width=iw:height=50:t=50","drawtext=fontfile=/usr/share/fonts/gnu-free/FreeMono.ttf: text='CIRCLE': fontsize=30: x=10: y=((50-th)/2) : fontcolor=white","drawtext=fontfile=/usr/share/fonts/gnu-free/FreeMono.ttf: text='FOO_0010': fontsize=30: x=(w-tw)/2: y=((50-th)/2) : fontcolor=white","drawtext=fontfile=/usr/share/fonts/gnu-free/FreeMono.ttf: text='%{localtime\:%Y-%m-%d %a %T}': fontsize=30: x=(w-tw-10): y=((50-th)/2) : fontcolor=white","drawtext=fontfile=/usr/share/fonts/gnu-free/FreeMono.ttf: text='$USER comp v001': fontsize=30: x=10: y=h-50+((50-th)/2): fontcolor=white","drawtext=fontfile=/usr/share/fonts/gnu-free/FreeMono.ttf: timecode='09\:57\:00\:00': r=23.976: fontsize=30: x=(w-tw)/2: y=h-50+((50-th)/2): fontcolor=white","drawtext=fontfile=/usr/share/fonts/gnu-free/FreeMono.ttf: text='%{n}': start_number=100: r=23.976: fontsize=30: x=(w-tw-10): y=h-50+((50-th)/2): fontcolor=white" -y output.mov
```

한프레임만 슬레이트를 넣는 상황에서도 아래 코드는 잘 작동합니다.
```
ffmpeg -i ~/examples/FOO_0010/FOO_0010.0100.jpg -vf "drawbox=x=0:y=0:w=iw:h=50:color=black@0.3:width=iw:height=50:t=50","drawbox=x=0:y=ih-50:w=iw:h=ih:color=black@0.3:width=iw:height=50:t=50","drawtext=fontfile=/usr/share/fonts/gnu-free/FreeMono.ttf: text='CIRCLE': fontsize=30: x=10: y=((50-th)/2) : fontcolor=white","drawtext=fontfile=/usr/share/fonts/gnu-free/FreeMono.ttf: text='FOO_0010': fontsize=30: x=(w-tw)/2: y=((50-th)/2) : fontcolor=white","drawtext=fontfile=/usr/share/fonts/gnu-free/FreeMono.ttf: text='%{localtime\:%Y-%m-%d %a %T}': fontsize=30: x=(w-tw-10): y=((50-th)/2) : fontcolor=white","drawtext=fontfile=/usr/share/fonts/gnu-free/FreeMono.ttf: text='$USER comp v001': fontsize=30: x=10: y=h-50+((50-th)/2): fontcolor=white","drawtext=fontfile=/usr/share/fonts/gnu-free/FreeMono.ttf: timecode='09\:57\:00\:00': r=23.976: fontsize=30: x=(w-tw)/2: y=h-50+((50-th)/2): fontcolor=white","drawtext=fontfile=/usr/share/fonts/gnu-free/FreeMono.ttf: text='%{n}': start_number=100: fontsize=30: x=(w-tw-10): y=h-50+((50-th)/2): fontcolor=white" -y output.jpg
```

## 슬레이트 디자인시 자주 사용되는 옵션
- `w`, `W`, `width`
- `h`, `H`, `height`
- `iw` : image width
- `ih` : image height
- `tw`, `text_w` : text width
- `th`, `text_h` : the height of the renderd text
- `line_h`, `lh` : the height of each text line
- `t` : 두께
- `x` : x 좌표
- `y` : y 좌표
- `n` : the number of input frame, starting from 0
- `%{localtime\:%Y-%m-%d %T}` : timestamp

## 유닉스 타임을 가지고 오는 방법
```bash
$ date +%s
```

## Reference
- 자(Feet) 연산 : https://lists.ffmpeg.org/pipermail/ffmpeg-user/2017-April/035849.html