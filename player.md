# Player
미디어를 다루다보면 미디어 종류에 따라서 재생할 수 있는 미디어가 다르다는 것을 알 수 있습니다.

## Mplayer

## DJV View
오픈소스 플레이어입니다. EXR 시퀀스를 확인할 때 사용하기 좋습니다.

http://djv.sourceforge.net

## RV player
아마도 대부분의 VFX회사에서는 이 플레이어를 사용합니다.
샷건 파이프라인툴을 사용하면 이 플레이어를 무료로 사용할 수 있습니다.

- http://www.tweaksoftware.com
- Download : http://www.tweaksoftware.com/downloads/tweak-software-license-terms-and-conditions

#### prores 코덱 활성화하기
주의! 이 방식을 사용하면 법적 책임이 발생할 수 있습니다.
prores코덱을 재생하도록 배포시 RV 플레이어에서 기본적으로 지원하지 않는 이유는
아래 나열된 코덱은 독점권, 지적 재산권 하에서 보호되는 알고리즘이 사용되기 때문입니다. 이 코덱을 실제로 사용하기 위해서는 적절한 라이센스와 권리가지고 사용해야 하며 무단으로 사용하게 되면 그에 따른 책임이 발생할 수 있습니다.
만약 책임지기 싫다면 항목에서 제거하고 컴파일하여 사용하지 말아주세요.

이 내용은 init.cpp 파일 상단 주석에도 표기되어 있습니다.

RV가 설치된 폴더로 이동합니다.
```
$ cd src/mio_ffmpeg
$ vim init.cpp
```

init.cpp 중 아래 항목에 대한 코드가 보입니다.
```
static const char* disallowedCodecsArray[] = {
    "mp3",
    "ac3",
    "hevc",
    "mpeg2video",
    "prores",
    "prores_aw",
    "prores_ks",
    "prores_lgpl",
    "svq1",
    "svq3",
    0 };
```

코드를 아래처럼 바꾸어주세요.
```
static const char* disallowedCodecsArray[] = {
    0 };
```


저장후 빠져나와 아래 처럼 컴파일 합니다.

```
$ make
$ make install
```

컴파일시 아래 에러가 난다면..
```
warning: include path for stdlibc++ headers not found; pass '-std=libc++' on the command line to use the libc++ standard library instead [-Wstdlibcxx-not-found]
```

Makefile 내용에서 아래항목을 다음 줄처럼 수정해주세요.

```
STD_CXXFLAGS = -std=gnu++98 -stdlib=libstdc++
```

```
STD_CXXFLAGS = -std=gnu++98 -stdlib=libc++
```

컴파일을 다시 해줍니다.