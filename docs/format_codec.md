# 동영상 포멧과 코덱
동영상 작업에 사용되는 포멧과 코덱은 굉장히 많습니다.
세상에는 굉장히 많은 포멧과 코덱이 존재합니다.
이 페이지는 실무에서 많이 사용되는 정보 및 미래에 많이 사용될 av1, vp9 코덱같은 정보를 포함하여 작성합니다.

## 포멧
#### .mov
애플에서 개발된 포멧입니다.
최종 작업물 전까지 동영상을 저장하기 위해서 가장 많이 사용합니다.
VFX 실무 분야에서는 `Prores mov 포멧` 또는 `H.264 mov 포멧`을 자주 사용합니다.
이 포멧을 만들기 위해 많은 회사들은 회사에 맞도록 자동화 컨버팅 프로그램을 제작합니다.

#### .mp4
MPEG에서 개발한 포멧입니다. .mov를 기반으로 개발되었습니다.
웹, 모바일에서 재생하기 위해서 실무에서 자주 컨버팅하는 상황이 발생합니다.
배포단계에서 많이 사용됩니다.

#### .mkv
[Matroska](https://www.matroska.org/) 팀에서 개발중인 컨테이너.
비디오, 오디오, 자막, 챕터 정보를 하나로 저장가능 합니다. 상용툴과 호환이 떨어져서 실무에서는 사용이 저조합니다.

#### .webm
구글에서 개발된 동영상 컨테이너. .mkv 기반으로 만들어진 포멧입니다. vp8, vp9 코덱이 이 컨테이너에 저장되는 경우가 많습니다.

#### 기타 동영상 컨테이너
https://en.wikipedia.org/wiki/Comparison_of_video_container_formats

## 코덱
### Apple Prores
Apple에서 제작 관리되는 코덱입니다. 파이널컷 프로 Base에서 업무하는 회사와 일을 할 때 이 포멧을 요구하는 경우가 많습니다.

코덱의 종류
- Prores 4444XQ
- Prores 4444
- Prores 422HQ : 실무에서 자주 사용됨
- Prores 422
- Prores 422LT : 실무에서 자주 사용됨
- Prores Proxy : Onset(현장)에서 자주 사용됨

https://support.apple.com/ko-kr/HT200321

### H.264
동영상을 배포하기 위해서 가장 많이 사용되는 코덱입니다.
H.264 기술을 상업적으로 사용하려면 MPEG LA 단체 및 기타 특허 소유자에게 로열티를 지불해야합니다.

### HEVC / H.265
해상도가 점점 커짐에 따라 H.264 기술을 기반으로 제작된 코덱입니다. 성능은 좋지만 구글, 넷플릭스같은 기업들은 로열티 프리형태의 코덱으로 서비스 원하고 있습니다.
- 8192×4320, 8K UHD를 지원합니다.

### Avid DNx 시리즈
Avid에서 제작 관리되는 포멧입니다. Avid 장비를 사용하는 업체와 일할 때 이 코덱을 요구하는 경우가 많습니다.

다운로드 : http://avid.force.com/pkb/articles/en_US/download/en423319

### AV1
Google, Apple, Microsoft, Amazon, Facebook, Netflix, Nvidia 등의 기업이 참여하며 만들고 있는 코덱입니다.

- 샘플파일 : http://download.opencontent.netflix.com/?prefix=AV1/

#### 샘플파일 재생방법
크롬베타를 설치합니다. https://www.google.com/intl/ko_ALL/chrome/beta/
URL입력창에서 `chrome://flags` 로 접근하여 Search flags에 `AV1`으로 검색합니다. Enable AV1 video decoding 가 활성화 되어있는지 체크해주세요.

### vp8 / vp9
로열티가 없는 오픈소스 코덱이며 구글이 개발중입니다. Youtube 등 동영상 서비스에 이미 사용중입니다.

- 샘플파일 : https://developers.google.com/media/vp9/get-started/#step_1_get_sample_video


## Reference
- Youtube가이드 : https://support.google.com/youtube/answer/1722171?hl=en
- https://blendermarket.com/posts/reduce-the-size-of-your-training-videos
- An Alliance of Global Media : https://aomedia.org
- 로열티비용 : https://en.wikipedia.org/wiki/High_Efficiency_Video_Coding#Patent_license_terms
- 코덱리스트 : https://en.wikipedia.org/wiki/List_of_codecs​
