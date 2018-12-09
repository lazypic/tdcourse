# EDL
Edit Decision List 편집정보가 담긴 아스키 파일입니다.
서로 다른 편집툴간 데이터를 주고 받기 위해서 개발된 포멧입니다.
Adobe Premiere Pro, Avid Media Composer, Apple Final Cut Pro 등등의 편집툴에서 import, export 할 수 있습니다.
편집실과 이야기하여 .edl 파일을 잘 받을 수 있다면 VFX 샷 작업시 각 샷의 길이를 알아내는 확실한 방법입니다.

## 파일 구성
보통 .edl 파일의 내용은 아래형태를 띕니다.
```
TITLE: Sequence 01
FCM: NON DROP FRAME

001  A006C022_161208_R10A       V     C        01:00:00:00 01:00:59:24 00:00:00:00 00:00:59:24
* FROM CLIP NAME: Jellyfish.jpg

002  A006C023_161208_R10A       AA    C        00:00:00:00 00:01:30:00 00:00:00:00 00:01:30:00
* FROM CLIP NAME: N5_final screensaver_mp4.mov

003  A006C024_161208_R10A       V     C        00:00:00:00 00:00:30:01 00:00:59:24 00:01:30:00
* FROM CLIP NAME: Test rename
AUD  3    4

004  A007C002_161208_R10A       V     C        00:00:00:00 00:00:24:17 00:01:30:00 00:01:54:17
* FROM CLIP NAME: Test rename

005  A007C004_161208_R10A       V     C        00:00:24:17 00:00:24:17 00:01:54:17 00:01:54:17
005  A007C004_161208_R10A       V     D    070 00:59:58:21 01:00:05:14 00:01:54:17 00:02:01:10
EFFECTS NAME IS CROSS DISSOLVE
* FROM CLIP NAME: Test rename
* TO CLIP NAME: Jellyfish.jpg

006  A007C005_161208_R10A       AA    C        00:00:00:00 00:00:29:01 00:01:30:00 00:01:59:01
* FROM CLIP NAME: Test rename

007  A007C006_161208_R10A       AA    C        00:00:29:01 00:00:29:01 00:01:59:01 00:01:59:01
007  A007C007_161208_R10A       AA    W001 025 00:00:00:00 00:00:10:20 00:01:59:01 00:02:10:21
EFFECTS NAME IS Constant Power
* FROM CLIP NAME: Test rename
* TO CLIP NAME: BL

008  A007C008_161208_R10A       V     C        01:00:00:00 01:00:05:00 00:02:01:10 00:02:06:10
* FROM CLIP NAME: Black Video

009  A007C009_161208_R10A       V     C        01:00:10:14 01:00:15:00 00:02:06:10 00:02:10:21
* FROM CLIP NAME: Jellyfish.jpg

010  A007C010_161208_R10A       V     C        00:00:00:00 00:00:30:01 00:02:10:21 00:02:40:22
* FROM CLIP NAME: Test rename
M2   A007C010_161208_R10A       037.5                      00:00:00:00 

011  A007C011_161208_R10A       AA    C        00:00:00:00 00:00:30:01 00:02:10:21 00:02:40:22
* FROM CLIP NAME: Test rename
M2   A007C011_161208_R10A       037.5                      00:00:00:00
```

순서, Reelname, 채널, 트렌지션, 소스 IN타임코드, 소스 OUT타임코드, 편집 IN타임코드, 편집 OUT타임코드 순으로 구성되어 있습니다.

- TITLE : EDL 파일의 제목입니다.
- FCM : Frame Code Mode의 약자입니다. 편집시 Drop Frame 모드인지 None Drop Frame 모드인지 알려주는 장치 입니다.
- 숫자 : 보통 3자리의 숫자로 되어있습니다. 0-999
- Reel네임(소스이름) : 장비에 따라 최대 8자리로 제한된 소프트웨어도 있습니다. A-Z, 0-9 문자만 사용할 수 있습니다. .edl 포멧마다 최대 7자리의 문자만 사용할 수 있기 때문에 이 특징이 파이프라인을 작성할 때 그대로 반영되는 경우가 많습니다. 예) 샷이름이 `FOO_0010`, `BAR_0010` 형태가 결국 될 수 밖에 없는 이유.

- 채널 : 툴마다 표기문자가 조금씩 다릅니다.
    - V : 비디오 채널, V1, V2 형태등 많은 패턴이 존재합니다.
    - A : 오디오 채널, A1, A2 형태등 많은 패턴이 존재합니다.

- 트렌지션
    - C : 컷
    - D : 디졸브. 디졸브가 들어가면 이후 몇 프레임으로 디졸브 되는지 프레임 정보가 표기됩니다.
    - W : Wipe 트렌지션

- M2 : 중요! M2 이벤트는 리타임 되었다는 뜻입니다. VFX샷에서 작업시 주의를 요하는 샷입니다. 이런 샷만 모아서 작업시 아웃풋 데이터를 자동 체크하도록 만들기도 합니다. 퍼센트로 바꾸기 위해서 `M2 * (1/100)` 값을 적용하여 이후에 제작 파이프라인 상에서 사용하기 도 합니다.

## edl 파이썬 파서
- https://github.com/simonh10/python-edl

.edl 파일 안에는 타임코드 정보가 있습니다. 이 타임코드를 파싱할 때는 
https://code.google.com/archive/p/pytimecode/ 라이브러리를 사용하세요. 물론 직접 작성하는 것도 이론을 이해하기에 좋습니다.

## Reference
- http://resources.avid.com/SupportFiles/attach/EDLManagerGuide_4.0_8.0.pdf
- http://www.niwa.nu/2013/05/how-to-read-an-edl/
- http://www.edlmax.com/EdlMaxHelp/Edl/maxguide.html
- http://www.niwa.nu/2013/05/how-to-read-an-edl/