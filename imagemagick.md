# ImageMagick
이미지를 변환, 편집, 합성할 때 사용하는 오픈소스 이미지 연산 유틸리티 입니다.
인식하는 이미지 파일은 약 200여개 정도 됩니다.


## 설치
Imagemagick은 yum 을 이용해서 간단하게 설치 할 수 있습니다.
`ImageMagick 6.7.8-9` 버전이 설치 됩니다.
```
# yum install ImageMagick
```

## 실무에서 자주 사용하는 명령어

#### compare
두 이미지가 같은지 확인할 때 사용합니다.
저는 a.dpx와 b.dpx의 결과가 같은지 확인할 때 간혹 사용하였습니다.
회사에서 작업하다보면 이전에 나간 아웃풋 결과와 이후 나갈 아웃풋 결과가 같은지 체크할 상황이 많이 발생합니다.
기존 작업이 OK 되었어도 이후 아티스트가 좀더 작업하는 경우가 실수로 많이 발생합니다.
후반작업 이후 입체 컨버팅같은 작업이 남아있을 때는 클라이언트가 OK플레이트와 회사에서 최종 작업한 플레이트의 아웃풋에 오차가 있는지 간단하게 확인할 때 사용할 수 있습니다.

```
$ compare -metric MAE a.dpx b.dpx /tmp/diff.dpx

480.728 (0.00733544) # 다르면 이런 형태의 숫자가 나옵니다.
0 (0) # 두 이미지가 같다면 0 값이 출력됩니다.
```

#### convert
많은 명령어중 아마도 여러분은 convert 명령어를 가장 많이 사용하게 됩니다.
일반적으로 이미지를 컨버팅 할 때 자주 사용합니다. 썸네일 이미지를 생성할 때도 사용합니다.
LUT를 적용하거나 수많은 컬러스페이스를 연산하기 위해서는 oiiotool을 더 많이 사용하게 됩니다.

jpg 이미지를 png로 바꾸는 예제
```
$ convert a.jpg a.png
```

dpx이미지를 jpg로 바꾸는 예제
```
$ convert a.dpx a.jpg
```

위처럼 DPX를 jpg로 바꾸면 뿌연 이미지가 출력됩니다. .dpx는 Log 컬러스페이스 보통 가지고 있습니다. 컬러스페이를 바꾸기 위해서는 아래처럼 추가적인 셋팅이 필요합니다.
```
$ convert a.dpx -set colorspace Log -colorspace sRGB a.jpg
```


비율을 고정한 상태에서 사용하는 이미지 리사이즈 예제
```
$ convert 1318_021092.dpx -resize 50% test.jpg
```


사이즈를 넘기면 자동으로 잘라내는 형태의 이미지 리사이즈(Crop됩니다.)
```
$ convert test.jpg -resize 360x240^ -gravity center -extent 360x240 thumb.jpg
```

LetterBox 형태의 이미지 리사이즈(나머지 영역은 검정색으로 채워집니다.)
```
$ convert test.jpg -thumbnail 360x240 -background black -gravity center -extent 360x240 thumb.jpg
```

#### identify
이미지 정보를 분석할 때 사용합니다.
보통 저는 [mediainfo](mediainfo.md)를 더 많이 사용합니다.

```
$ identify test.png
$ identify -verbose test.png
```

#### import
스크린캡쳐를 위한 유틸리티를 제작할 때 사용합니다.

```
$ import screen.jpg
$ import -window root screen.jpg
```

#### montage
여러 이미지를 묶어서 하나의 이미지로 만들 때 사용합니다.

사용예 : https://imagemagick.org/Usage/montage/


## 실무에서 자주 사용하지 않는 명령어
아래 명령어는 메뉴얼만 봐두었다가 필요시 사용하세요.

- animate : 애니메이션 시퀀스를 묶어서 볼 때 사용합니다.
- composite : 2개 이상의 이미지를 합성할 때 사용합니다.
- conjure
- display : 이미지를 볼 때 사용합니다.
- mogrify : convert명령어와 비슷합니다. 오리지널 파일을 덮어쓰기 때문에 실무에서는 사용하지 않습니다.
- stream

## 샘플파일
[샘플파일 다운로드](sample.md)
