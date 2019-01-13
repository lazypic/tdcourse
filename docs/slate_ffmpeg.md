# FFmpeg를 이용한 슬레이트 제작

w, W, width
h, H, height
iw : image width
ih : image height
tw : text width
th : the height of the renderd text
line_h, lh : the height of each text line
x
y

```
ffmpeg -f image2 -start_number 100 -r 24 -i ~/examples/FOO_0010/FOO_0010.%4d.jpg  -vcodec libx264 -vf "drawbox=x=0:y=0:w=iw:h=50:color=black@0.5:width=iw:height=50:t=50","drawbox=x=0:y=ih-50:w=iw:h=ih:color=black@0.5:width=iw:height=50:t=50","drawtext=fontfile=/usr/share/fonts/gnu-free/FreeMono.ttf: timecode='09\:57\:00\:00': r=23.976: fontsize=30: x=(w-tw)/2: y=(h-th)-10: fontcolor=white" -y output.mov
:text='CIRCLE': fontsize=30: x=(w-tw)/2: y=h-(2*lh): fontcolor=white: box=1: boxcolor=0x00000099"
```

```
ffmpeg -f image2 -start_number 100 -r 24 -i ~/examples/FOO_0010/FOO_0010.%4d.jpg  -vcodec libx264 -vf "drawbox=x=0:y=0:w=iw:h=50:color=black@0.5:width=iw:height=50:t=50","drawbox=x=0:y=ih-50:w=iw:h=ih:color=black@0.5:width=iw:height=50:t=50","drawtext=fontfile=/usr/share/fonts/gnu-free/FreeMono.ttf: text='CIRCLE': fontsize=30: x=10: y=((50-th)/2) : fontcolor=white","drawtext=fontfile=/usr/share/fonts/gnu-free/FreeMono.ttf: timecode='09\:57\:00\:00': r=23.976: fontsize=30: x=(w-tw)/2: y=h-50+((50-th)/2): fontcolor=white" -y output.mov
```