# 리눅스에서 Beep음 제거하기
강의실에서는 여러 사람들이 프로그래밍 하기 때문에 리눅스에서 나오는 Beep음이 타인에게 굉장히 거슬립니다. Beep음 제거하는 방법을 알아보겠습니다.

## xterm
```
$ echo "xset b off" >> ~/.xession
```

## bash shell
```
$ echo "set bell-style none" >> ~/.inputrc
```

## vim
```
$ echo "set vb" >> ~/.vimrc
```

## 실습
root 계정도 똑같이 셋팅해주세요.