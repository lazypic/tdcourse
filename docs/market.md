# 개발자의 시선으로 바라보는 시장의 흐름.

## 데이터를 저장하는 포멧은 이제 대부분 OpenSource로 개발 되어있습니다.
이미 많은 회사들은 내부에서 사용하는 포멧을 초기부터 공개하여 시장 표준이 되도록 하는 전략을 취하고 있습니다.

- OCIO : OpenColorIO
- OIIO : OpenImageIO
- OTIO : OpenTimelineIO
- OpenEXR
- OSL : OpenShadingLanguage
- ABC : Alembic
- USD
- Ptex
- OpenSubdiv
- OpenVDB

각 개발된 라이브러리, 포멧만 잘 사용하더라도 해외 유명한 스튜디오와 작업구조의 차이가 크게 나지 않습니다.

## 상용 소프트웨어들도 오픈소스 진형에서 사용하고 있는 전략중 장점들을 채용하여 마케팅 전략으로 시장에 반영하고 있습니다.
- 교육용 버전 또는 일정 해상도 작업까지는 무료화
    - [Nuke PLE 버전](https://www.foundry.com/products/nuke/non-commercial)
    - [Renderman Non-Commercial](https://renderman.pixar.com/intro)
    - [Houdini apprentice](https://www.sidefx.com/products/houdini-apprentice/)
- 제품 출시 이후 일정 수익을 분배하는 구조
    - Unreal Engine

## 데이터 연결의 시대
일부 툴을 제외한 꽤 많은 그래픽스 툴들은 위에 설명드렸던 포멧을 불러오고 저장할 수 있습니다.
또한 오픈소스 파일 포멧들은 따로 상용툴 없이도 터미널을 이용해서 간단한 파일 매니징이 가능합니다.
여러분이 만약 파이프라인 관련툴을 개발한다면, 툴을 설계하기전에 시장에서 사용하고 있는 정보들을 먼저 리서치하고 설계해주세요.


## 인하우스툴이 상용소프트웨어로 바뀌고 다시 Saas 서비스로 바뀐다.
- 뉴크, 마리, 카타나 같은 VFX회사 내부 인하우스 툴을 Foundry가 채택하여 시장에 배포하는 형태로 비즈니스 모델이 발전되어 왔습니다.
- 과거 인하우스로 제작되던 프로젝트 매니지먼트 툴들이 Sass서비스 형태로 변경. 예) shotgrid 서비스
