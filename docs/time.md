# Time
시간과 관련된 명령어를 다루어 보겠습니다.

date 명령어는 날짜와 시간, 국가를 출력합니다.
```bash
$ date
2018. 12. 15. (토) 00:11:45 KST
```

timedatectl 명령어를 이용해서 시간과 관련된 많은 정보를 볼 수 있습니다.
```
$ timedatectl
      Local time: 토 2018-12-15 00:12:35 KST
  Universal time: 금 2018-12-14 15:12:35 UTC
        RTC time: 금 2018-12-14 15:12:35
       Time zone: Asia/Seoul (KST, +0900)
     NTP enabled: yes
NTP synchronized: yes
 RTC in local TZ: no
      DST active: n/a
```

- [KST](https://ko.wikipedia.org/wiki/한국_표준시) : Korea Standard Time (KST = UTC + 9)
- [UTC](https://namu.wiki/w/협정%20세계시) : Coordinated Universal Time 협정 세계시
- [RTC](https://ko.wikipedia.org/wiki/실시간_시계) : Real Time Clock
- [NTP](https://ko.wikipedia.org/wiki/네트워크_타임_프로토콜) : Network Time Protocol
- TZ : Time Zone의 약자
- [DST](https://ko.wikipedia.org/wiki/일광_절약_시간제) : Daylight saving time, 써머타임
- PST : 태평양 표준시, 미국, 캐나다, 멕시코

## NTP를 이용해서 시간동기화
```
# timedatectl set-ntp true
```

- 한국 NTP 서버 : https://www.pool.ntp.org/zone/kr

## 시간동기화가 필요한 이유
회사에서 많은 컴퓨터로 작업을 할 때 모든 컴퓨터의 시간이 맞는것은 좋은 습관입니다.
서버, 렌더팜, 작업자 컴퓨터의 시간이 서로 오차가 있다면,
시간관련된 프로그래밍시 각 장비마다 오차가 발생할 소지가 높습니다.
특히나 인터넷이 연결되지 않는 네트워크 환경에서는 타임서버를 만들고 해당 서버를 통해서 동기화 하는 방법이 필요할 수 있습니다.


## 시간대 변환툴
국제 온라인 세미나, 강연등을 들을 때 도움이 됩니다.

https://www.timeanddate.com/worldclock/converter.html
