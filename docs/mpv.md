# mpv
홈페이지 : https://mpv.io/

영상을 볼 때 사용하는 플레이어 입니다. 예전에는 mplayer를 사용했지만 mpv는 mplayer, mplayer2를 Fork 하여 개발중인 차세대 영상 플레이어 입니다.

열심히 CentOS7을 설치했는데 영화 한편 볼 수 없다면 너무 슬플것 같지 않나요?
그래서 준비했습니다. mpv 설치방법을 기록해 둡니다.

![mpv](https://mpv.io/images/mpv-screenshot-34cd36ae.jpg)

설치 방법은 아래와 같습니다.
```
# yum install yasm
# yum install fribidi
# yum install youtube-dl
# yum install freetype-devel
# yum install fribidi-devel
# yum install fontconfig-devel
# yum install harfbuzz-devel
# yum install cmake
# yum install mercurial
# yum install nasm
# yum install openssl-devel
# yum install libX11-devel
# yum install python-docutils
# yum install luajit-devel
# yum install libbluray-devel
# yum install libdvdread-devel
# yum install libcdio-paranoia-devel
# yum install lcms2-devel
# yum install pulseaudio-libs-devel
# yum install jack-audio-connection-kit-devel
# yum install alsa-lib-devel
# yum install libdrm-devel
# yum install libxkbcommon-devel
# yum install libXScrnSaver-devel
# yum install libXext-devel
# yum install libXv-devel
# yum install PyQt4-devel
# yum install libvdpau-devel
# yum install libva-devel
# yum install gstreamer1-vaapi-devel
# yum install libcaca-devel
# cd ~/app
# git clone https://github.com/mpv-player/mpv-build.git mpv_src
# cd mpv_src
# mkdir mpv-build
# echo --enable-openssl >> ffmpeg_options
# echo --enable-nonfree >> ffmpeg_options
# ./rebuild -j4 # 오래걸립니다.
# ./install
```

잘 작동되는지 확인해 봅시다. 터미널에서 아래처럼 타이핑 해보세요.
```
$ mpv https://www.youtube.com/watch?v=O1qJ5FcV__0
```
