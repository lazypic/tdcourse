# .bashrc

이 장은 실습입니다.

## init.env 파일 만들기
~/env 폴더를 만들어주세요. 자신이 원하는 셋팅을 추가합니다.
이 디렉토리는 나중에 git을 배울때 버전관리가 되는 디렉토리로 바뀔 예정입니다.
저는 env폴더에 init.env 파일을 만들어 보겠습니다.

~/env/init.env 에 내용을 작성해봅시다. 알리아스를 최근에 배웠으니 아래 명령어를 추가해봅시다.

```
alias weather="curl wttr.in/seoul"
alias curriculum="firefox https://github.com/cgiseminar/curriculum"
```

## .bashrc에 custom.env 파일 물리기
~/.bashrc 파일에 source 합니다.
```
source $HOME/env/init.env
```

터미널을 새로 띄워서 weather 라고 타이핑해보세요.

## 실습
- `n` 이라는 문자를 타이핑하면 뉴크가 실행되도록 해보세요.
