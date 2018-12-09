# Shell
대부분 우리가 사용하는 Shell은 bash 쉘이지만,
Shell 이름정도를 알아두면 나중에 당황하지 않고,
Shell 임을 빠르게 인식할 수 있습니다.

## bash
우리 커리큘럼에서는 bash 쉘을 사용할 예정입니다.
- https://en.wikipedia.org/wiki/Bash_(Unix_shell)

## tcsh / csh
FreeBSD Unix를 사용하는 분야로 가지 않으면 보통 만날일을 없습니다.

- https://en.wikipedia.org/wiki/Tcsh

## ksh(kornshell)
- https://en.wikipedia.org/wiki/KornShell

## zsh
- https://en.wikipedia.org/wiki/Z_shell

## fish
사용자와 인터렉티브한 측면을 강조한 쉘입니다.
```
# yum install fish
```

## 알아두면 좋은점
간혹 크레커 들은 시스템이 침투하여 shell을 바꾸어서 작업하고 합니다.
초보 시스템어드민의 경우에는 다른 쉘의 경험이 적기 때문에 잘 모르기도 하거든요.

영화 "인셉션"에서는 주인공이 꿈속에서 다시 꿈속을 들어갑니다.
shell의 세계에서도 가능합니다.
shell에서 다른 shell로 들어갈 수 있습니다. 아래 예제처럼 말이죠!

```
$ tcsh
$ csh
$ bash
$ exit # bash 를 빠져나온다.
$ exit # csh 을 빠져나온다.
$ exit # tcsh 을 빠져나온다.
```


