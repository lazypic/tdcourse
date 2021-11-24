# 촬영 데이터의 이름

Alexa, Red 카메라등으로 촬영을 하면 파일들이 외장 스토리지에 파일이 생성됩니다.
보통 다음과 같은 이름이 생성됩니다. 기종마다 다르지만 대부분 비슷한 양식을 가지고 있습니다.

```
A007C006_160424_R28L.ari // Arri사
A007_C006_160424_001.r3d // Red사
CAMNAME_1_2000-08-06_2347_C0001.mov // BlackMagic사
```

가장 많이 사용하는 Arri 형태로 설명하곘습니다.

- Camera index : A
- Camera Reel Count(001-999) : 007
- Cut : C
- Cut Count(001-999) : 006
- Time : 160424
- 렌덤하게 생성되는 자동코드 (추후 편집툴에서 수많은 데이터가 섞였을 때 고유함을 만드는 역할을 합니다.) : R28L

위 특징을 알고 있다면 추후 해당 데이터를 가지고 프로그래밍할 때 데이터 이해하기 쉽습니다.

특정 편집장비는 `A007C006_160424_R28L` 문자가 길어서 실제 출력할 때는 앞자리와 뒷자리 문자를 섞어서 `A007R28L` 형태로 줄여서 출력하기도 합니다.

## 촬영데이터 관찰

[샘플파일](sample.md) 다운로드

## 회사에서는..

위 이름처럼 복잡하게 들어온 데이터를 정리, 분배하는 툴을 제작해서 사용한답니다.

보통 대량의 촬영 데이터를 자주 사용하는 샷 구조로 쉽게 만드는 툴을 제작해서 사용합니다.

 ```bash
 /project/circle/in/A007C006_160424_R28L/A007C006_160424_R28L.######.exr

 데이터를
 
 /project/circle/shot/FOO/0010/plate/FOO_0010_plate_v001/FOO_0010_plate_v001.####.exr
 
 로 변환하는 툴
 ```

## Reference

- https://www.arri.com/forum/viewtopic.php?f=48&t=274
- http://michaelkammes.com/editorial/deciphering-the-red-file-name/