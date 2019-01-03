# Shell
쉘은 OS와 사용자를 연결해주는 인터페이스 입니다. 터미널, GUI 방식이 있습니다.

대부분 우리가 사용하는 Shell의 종류는 bash 쉘이지만 과거부터 현재까지 많은 Shell들이 만들어 지거나 만들어지고 있습니다. Shell의 이름정도를 알아두면 나중에 여러 OS를 만나더라도 당황하지 않고 Shell 이름임을 빠르게 인식할 수 있습니다.

## Bash
가장 많이 사용되는 Shell입니다. 커리큘럼에서는 bash 쉘을 사용합니다.

- https://en.wikipedia.org/wiki/Bash_(Unix_shell)

## Tcsh / Csh
- [FreeBSD Unix](https://namu.wiki/w/FreeBSD)를 사용하는 분야로 가지 않으면 보통 여러분이 만날일은 없습니다.
- FreeBSD 사용분야 : 플레이스테이션, 닌텐도 스위치

- https://en.wikipedia.org/wiki/Tcsh

## ksh(kornshell)
- https://en.wikipedia.org/wiki/KornShell

## zsh
- https://en.wikipedia.org/wiki/Z_shell

zsh Shell 설치
```
$ su
# yum install zsh
# exit
$ zsh
```

## fish
사용자와 인터렉티브한 측면을 강조한 쉘입니다.

유투브보기 : https://www.youtube.com/watch?v=8pno3tTdywg

fish Shell 설치
```
$ su
# yum install fish
# exit
$ fish
```

## 알아두면 좋은점
간혹 크래커들이 시스템이 침투하여 shell을 바꾸어서 작업하곤 합니다.
초보 시스템 관리자의 경우에 다른 쉘의 경험이 적기 때문에 잘 모르기도 하거든요.
수많은 쉘에서 벌어지는 작업을 초보자가 추적하기 쉽지도 않구요~

영화 "인셉션"에서는 주인공이 꿈속에서 다시 다른 꿈속으로 들어갑니다.
Shell의 세계에서도 가능합니다.
Shell에서 다른 Shell로 들어갈 수 있습니다. 아래 예제처럼 말이죠!

```
$ tcsh
$ csh
$ bash
$ exit # bash 를 빠져나온다.
$ exit # csh 을 빠져나온다.
$ exit # tcsh 을 빠져나온다.
```

## 실습
- 각 페이지의 링크를 클릭해서 자료를 읽어보세요.