# mencoder

수많은 mov 파일을 이어 붙힐 때 사용합니다.

설치
```bash
# yum install mencoder
```

```bash
$ mencoder -oac copy -ovc copy first.0001-0100.mov second.0101-0200.mov -o all.mov
```