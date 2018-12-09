# man
man 명령어는 각 명령어의 메뉴얼을 볼 수 있도록 도와주는 명령어입니다.

ls 매뉴얼을 읽기위해서 아래처럼 터미널에서 타이핑 해주세요.
```bash
$ man ls
```

위 명령어의 Output은 아래와 같습니다.

```
LS(1)                     BSD General Commands Manual                    LS(1)

...
..
.
```
상단 `명령어(숫자)` 형태로 첫번째 줄이 구성되어있습니다.
메뉴얼을 읽을 때 이 숫자가 의미하는 것을 알고 메뉴얼을 읽으면 더욱 도움이 됩니다.

## 매뉴얼 코드 읽기
- 1 : 일반 명령어
- 2 : System Call(커널에 접근하기 위한 인터페이스)
    - 프로세서 제어(process Control)
    - 파일 조작(file manipulation)
    - 장치 관리(Device Management)
    - 정보 유지(Information maintenance)
    - 통신(Communication)
- 3 : C 함수 라이브러리
- 4 : 장치와 특수파일
- 5 : 파일 포멧, 
- 6 : Game, 재미있는 명령어들
- 7 : 프로토콜 규약, 문자셋 규약, 표준 파일시스템 구조, 등등을 다룹니다.
- 8 : 시스템 관리자 툴과 Daemons

## 메뉴얼 파일 위치

cd /usr/local/man

## Reference
- https://unix.stackexchange.com/questions/3586/what-do-the-numbers-in-a-man-page-mean