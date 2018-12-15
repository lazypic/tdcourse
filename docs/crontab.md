# Crontab
컴퓨터에 일정시간마다 실행되어야 하는 프로세스를 등록할 때 사용합니다.

## 예약하기
터미널에 아래처럼 타이핑합니다.

```
$ crontab -e
```
vi 에디터가 열립니다.명령어를 타이핑합니다.

## 시간설정 개념
- https://crontab.guru 에 접속하여 사이트 사용법을 설명합니다.

## 실습
우리 강의의 패턴을 정의하고 알람을 받아보는 예제를 다루어보겠습니다.
- 월~금 10시부터 18시 매 50분 : 휴식시간 알람
- 월~금 오후1시 : 점심시간 알람
- 월~금 오후6시 : 수업종료 알람

리눅스 wall 명령어는 터미널로 브로드 캐스트 메시지를 보내는 명령입니다.

```bash
$ echo "test" | wall

Broadcast message from woong@localhost.localdomain (Sat Dec 15 09:56:31 2018):

test
```

이제 crontab에 추가해 보겠습니다.

```bash
$ crontab -e 
```

```bash
50 10-18 * * 1-5 echo "break time" | wall
0 13 * * 1-5 echo "lunch time" | wall
0 18 * * 1-5 echo "end of lecture" | wall
```

매일 새벽 1시마다 python 백업스크립트를 실행합니다.
이런 패턴은 회사에서 개발과정에서 테스트할 때 자주 사용되는 패턴입니다.
매번 오래걸리는 컴파일의 경우에도 임시 빌드 시스템으로 사용하기 좋습니다.

```bash
* 1 * * * python /path/backup.py
```