# Arri Converter

Arri사에서 제작한 카메라로 찍은 Raw 데이터를 exr 같은 작업할 수 있는 데이터로 변환하는데 사용하는 툴입니다.

![arriconverter](https://i.ytimg.com/vi/7fDFfbSVz5w/maxresdefault.jpg)

## Arri Raw Converter

.ari 파일을 컨버팅 하기 위해서는 일반적으로 룩을 확인하기 위해서 arriraw_converter GUI 버전을 사용합니다.
소프트웨어는 아래에서 다운로드 받을 수 있습니다.

https://www.arri.com/en/learn-help/learn-help-camera-system/tools/arriraw-converter

.ari 데이터를 ACES exr로 아웃풋 하기 위한 옵션은 아래와 같습니다.
![raw_convert](../figures/arriraw_convert_aces.png)


## Command line 설치하기

작동 조건을 만들기 까다롭습니다.
직접 실습하지는 않습니다. 대부분 회사에서는 macOS 버전을 맞추어 사용합니다.


### Arri Converter cmd 설치

```bash
$ cd ~/app
$ wget https://www.arri.com/resource/blob/31840/da39200788aa6d14600fbb3fd6760251/arc-cmd-3-5-3-5-centos7-cpu-and-gpu-tar-data.gz --no-check-certificate
$ tar -xvzf arc-cmd-3-5-3-5-centos7-cpu-and-gpu-tar-data.gz
$ cd ARRIRAWConverter
$ ln -s libcudart.so.8.0.61 libcudart.so.8.0
```

ARRIRAWConverter를 실행하기 위해서는 아래 환경변수가 추가되어야 합니다.

```bash
$ export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$HOME/app/ARRIRAWConverter
```

### 필요한 라이브러리 설치

아래 문장이 뜨면 opencl-headers를 설치해야 합니다.
```bash
./ARC_CMD: error while loading shared libraries: libOpenCL.so.1: cannot open shared object file: No such file or directory
```

opencl-headers를 설치하는 방법

```bash
sudo yum install opencl-headers -y
```

### 다운로드

https://www.arri.com/en/learn-help/learn-help-camera-system/tools/arriraw-converter