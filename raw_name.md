# 촬영 데이터의 이름
Alexa, Red 카메라등으로 촬영을 하면 파일들이 외장 스토리지에 파일이 생성됩니다.
보통 다음과 같은 이름이 생성됩니다. 기종마다 다르지만 대부분 비슷한 양식을 가지고 있습니다.

```
A007C006_160424_R28L.ari
A007_C006_160424_001.r3d
```
- Camera index : `A`007C006_160424_R28L.ari
- Camera Reel Count(001-999) : A`007`C006_160424_R28L.ari
- Cut : A007`C`006_160424_R28L.ari
- Cut Count : A007C`006`_160424_R28L.ari
- Time : A007C006_`160424`_R28L.ari
- 렌덤하게 생성되는 자동코드 (추후 편집툴에서 수많은 데이터가 섞였을 때 고유함을 만드는 역할을 합니다.) : A007C006_160424_`R28L`.ari

특정 편집장비는 `A007C006_160424_R28L` 문자가 길어서 실제 출력할 때는 `A007R28L` 형태로 줄여서 출력하기도 합니다.

## Reference
- https://www.arri.com/forum/viewtopic.php?f=48&t=274
- http://michaelkammes.com/editorial/deciphering-the-red-file-name/