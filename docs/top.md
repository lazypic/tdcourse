# top

top 명령어는 시스템 리소스 모니터링 툴입니다.

터미널에서 top을 눌러서 실행합니다.

```bash
$ top
```

## 단축키

- q : 종료
- m : 메모리 정보. 계속 눌러보세요.
- t : 테스크 정보. t키를 계속 눌러보세요.
- n : 갯수를 설정할 수 있습니다. 10개만 보고 싶다면, n 키를 누르고 10을 타이핑하세요.
- k : kill 명령어입니다. pid를 입력하면 해당 프로세스가 종료합니다.
- u : 해당 유저만 볼 수 있습니다.
- f : 용어사전
- h : help
- j : 오른쪽 정렬
- z : color mode


## 실습

- 뉴크 렌더링을 진행하고 top명령어를 타이핑해서 시스템 점유율을 체크합니다.

## Tracker-Extract

CentOS에는 Tracker라는 데몬이 돌고 있습니다.
이 프로그램의 역할은 파일을 어디에 두었던지 상관없이 파일을 잘 찾기 위해서 인덱싱, 메타데이터들을 분석하는 프로그램 입니다. 이 프로그램의 문제점은 저사양의 노트북에서 이 서비스가 CPU를 많이 먹는다는 것입니다.

강제로 끄는 법은 아래과 같습니다.

아래 명령어를 터미널에 붙혀넣기 하고 Enter를 치세요.

```bash
tracker daemon -t
cd ~/.config/autostart
cp -v /etc/xdg/autostart/tracker-* ./
for FILE in `ls`; do echo Hidden=true >> $FILE; done
rm -rf ~/.cache/tracker ~/.local/share/tracker
```

### Reference

- https://gist.github.com/vancluever/d34b41eb77e6d077887c