# ffmpeg

동영상 변환툴

## 설치 : 이미 빌드되어있는 ffmpeg 설치하기
```
$ cd ~
$ mkdir -p app/ffmpeg
$ cd app/ffmpeg
$ wget http://johnvansickle.com/ffmpeg/builds/ffmpeg-git-64bit-static.tar.xz
$ tar xpvf ffmpeg-git-64bit-static.tar.xz --strip 1
```

## 사용법
```
$ ffmpeg -i input.mp4 output.avi
```

## 컴파일 설치방법
https://trac.ffmpeg.org/wiki/CompilationGuide/Centos
