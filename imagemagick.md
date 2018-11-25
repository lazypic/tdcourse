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
dpx를 비교하는 이미지 넣기.

#### convert
많은 명령어중 아마도 여러분은 convert 명령어를 가장 많이 사용하게 됩니다.

#### identify
이미지 정보를 분석할 때 사용합니다.
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
아래 명령어는 필요시 메뉴얼을 보고 파악해보세요.

- animate : 애니메이션 시퀀스를 묶어서 볼 때 사용합니다.
- composite : 2개 이상의 이미지를 합성할 때 사용합니다.
- conjure
- display : 이미지를 볼 때 사용합니다.
- mogrify : convert명령어와 비슷합니다. 오리지널 파일을 덮어쓰기 때문에 실무에서는 사용하지 않습니다.
- stream

## 샘플파일
[샘플파일 다운로드](sample.md)
