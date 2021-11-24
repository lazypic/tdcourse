# Arri Meta Extract

Arri 카메라 메타데이터를 추출하는 툴입니다.
카메라 렌즈를 각 프레임마다 어떻게 조작했는지, 카메라 정보등을 추출할 수 있습니다.
이 정보는 나중에 각 프레임별로 카메라 조작 정보가 바뀌는 상황(예를 들어 촬영자가 줌렌즈를 이용해서 자유롭게 조작시)에 매치무브를 할 때 유용한 정보가 됩니다.

![arrimetaextract](https://cdn.hdvideopro.com/2018/11/GunchBlog-2018-38-data.jpg)
Arri MetaExtract 소프트웨어를 이용하면 arri 데이터를 미리보기 할 수 있으며 .csv 파일로 뽑을 수 있습니다. 이 데이터는 파이썬을 이용해서 파싱할 수 있습니다.

![lds01](../figures/lds01.png)

Arri Raw converter 에서도 조작된 수치를 그래프로 볼 수 있는 기능을 제공합니다.

![lds02](../figures/lds02.png)
Arri Raw Converter 우측에도 자세한 정보를 미리 볼 수 있습니다.


![LDS](https://vmi.tv/upload/images/WLCS%20Essay/metadata.jpg)
LDS 시스템의 기본 구조

## 샘플파일 위치

[LDS example csv](https://github.com/lazypic/tdcourse_examples/blob/master/arriLDS/A003C025_150830_R0D0.csv) 미리보기

## Arri Converter cmd 설치

```bash
$ cd ~/app
$ wget https://www.arri.com/resource/blob/31892/10a22fb2884539fa3d9fdeeb89ae026d/arri-meta-extract-cmd-3-5-3-3-cent-os-7-data.zip --no-check-certificate
$ unzip arri-meta-extract-cmd-3-5-3-3-cent-os-7-data.zip
$ rm arri-meta-extract-cmd-3-5-3-3-cent-os-7-data.zip
$ cd ARRI_Meta_Extract_CMD 3.5.3.3_Cent_OS_7
```

## 뉴크에서 사용할 수 있는 플러그인

- http://www.nukepedia.com/python/misc/arri-alexa-metadata-extraction-for-nuke

## 다운로드 페이지

https://www.arri.com/en/learn-help/learn-help-camera-system/tools/arri-meta-extract

## 실습

- LDS .csv 파일을 파이썬으로 파싱해보자.
- 원하는 수치를 뽑아볼 것

## Reference

- https://www.hdvideopro.com/blog/metadata-tool-to-uncover-the-facts/