# Arri Converter
Arri사에서 제작한 카메라로 찍은 raw 데이터를 exr 같은 작업할 수 있는 데이터로 변환하는데 사용합니다.

![arriconverter](https://i.ytimg.com/vi/7fDFfbSVz5w/maxresdefault.jpg)

## Arri Raw Converter
.ari 파일을 컨버팅 하기 위해서는 일반적으로 arriraw_converter GUI 버전을 사용합니다.
소프트웨어는 아래에서 다운로드 받을 수 있습니다.

https://www.arri.com/en/learn-help/learn-help-camera-system/tools/arriraw-converter

.ari 데이터를 ACES exr로 아웃풋 하기 위한 옵션은 아래와 같습니다.
![raw_convert](../figures/arriraw_convert_aces.png)


## command line 설치하기
작동 조건을 만들기 까다롭습니다.
직접 실습하지는 않습니다. 대부분 회사에서는 macOS 버전을 맞추어 사용합니다.


### Arri Converter cmd 설치
```
$ cd ~/app
$ wget https://www.arri.com/resource/blob/31840/da39200788aa6d14600fbb3fd6760251/arc-cmd-3-5-3-5-centos7-cpu-and-gpu-tar-data.gz --no-check-certificate
$ tar -xvzf arc-cmd-3-5-3-5-centos7-cpu-and-gpu-tar-data.gz
$ cd ARRIRAWConverter
$ ln -s libcudart.so.8.0.61 libcudart.so.8.0
```

```
$ export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$HOME/app/ARRIRAWConverter
```

### 필요한 라이브러리 설치
아래 문장이 뜨면 opencl-headers를 설치해야 한다.
```
./ARC_CMD: error while loading shared libraries: libOpenCL.so.1: cannot open shared object file: No such file or directory
```

그래픽카드 드라이버를 설치하고 실행할 것
```
# yum install opencl-headers
```

### 다운로드
https://www.arri.com/en/learn-help/learn-help-camera-system/tools/arriraw-converter