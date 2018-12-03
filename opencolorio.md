# ACES / OpenColorIO
ACES는 Academy Color Encoding Specification의 약자입니다.
OpenColorIO는 ACES 표준을 따르는 컬러메니징 솔루션입니다.

소니이미지웍스에서 개발되었습니다.

- 소스코드 : https://github.com/imageworks/OpenColorIO

#### OCIO를 지원하는 툴
- Renderman
- Vray
- Arnold
- Kantana
- Nuke
- Blender
- Krita
- Silhouette
- Hiero
- Rv
- Gaffer
- Natron

#### OpenColorIO-Configs 셋팅하기
기본적으로 뉴크에는 OCIO가 탑재되어있습니다. 만약 내부 버전보다 더 높은 버전을 사용하고 싶다면 아래 설정을 따라해주세요.

```
cd ~/app
git clone https://github.com/imageworks/OpenColorIO-Configs
```

뉴크에 기본 탑재된 OCIO가 아닌 위 Configs 파일을 이용하고 싶다면 .bashrc에 OCIO경로를 지정하면 뉴크가 자동으로 인식하여 뉴크 실행시 OpenColorIO-Configs를 로딩합니다.

.bashrc
```
export OCIO=$HOME/app/OpenColorIO-Configs/aces_1.0.3/config.ocio
```

## Reference
- ociobakelut : http://opencolorio.org/CompatibleSoftware.html