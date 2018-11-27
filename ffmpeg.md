# ffmpeg
FFmpeg는 음성파일, 영상파일을 기록하거나 변환하는 오픈소스 프로그램입니다.

## 설치 : 이미 빌드되어있는 ffmpeg 설치하기
```
$ cd ~
$ mkdir -p app/ffmpeg
$ cd app/ffmpeg
$ wget http://johnvansickle.com/ffmpeg/builds/ffmpeg-git-64bit-static.tar.xz
$ tar xpvf ffmpeg-git-64bit-static.tar.xz --strip 1
```

## 명령어의 구성
- ffmpeg : 영상, 음성을 변환하는 툴
- ffprobe : 데이터를 분석하는 툴

## 지원하는 포멧과 코덱을 알아보기
자주 사용하게 될 코덱을 지원하는지 grep을 통해서 체크해보겠습니다.
```
$ ffmpeg -codecs
$ ffmpeg -codecs | grep prores
$ ffmpeg -codecs | grep dnxhd
$ ffmpeg -codecs | grep h264
$ ffmpeg -codecs | grep hevc
$ ffmpeg -codecs | grep vp9
$ ffmpeg -codecs | grep av1
$ ffmpeg -formats
```

예) AV1 코덱의 옵션을 알아보는 명령어는 아래와 같습니다.
```
$ ffmpeg -h encoder=libaom-av1
```

## 사용법
mp4를 avi로 변환하기
```
$ ffmpeg -i input.mp4 output.avi
```

jpg시퀀스를 H.264, fps 23.98 .mp4로 만들기
```
$ ffmpeg -f image2 -i /path/filename.%04d.jpg -c:v libx264 -r 23.98 output.mp4
```

input.mp4 영상 분석하기
```
$ ffprobe -v quiet -print_format json -show_format -show_streams input.mp4
```

## 컴파일 설치방법
https://trac.ffmpeg.org/wiki/CompilationGuide/Centos


## 레퍼런스
- ffmpeg와 비슷한 명령어 libav : https://www.libav.org
- ffmpeg와 libav의 분쟁 : http://klutzy.nanabi.org/blog/2012/11/16/ffmpeg-libav/