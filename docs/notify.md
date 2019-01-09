# 알림
프로그래밍을 하다보면 어떤 프로세스가 완료될 때,
사용자에게 알람을 해야하는 상황이 발생할 수 있습니다.
요즘 OS는 기본적으로 알람기능을 명령어로 제공한다.

## wall
```bash
$ echo "hello terminal notify" | wall
```

## CentOS / notify-send
CentOS에서는 알림을 주는 명령이 존재합니다. notify-send 명령어를 알아보겠습니다.

```bash
$ notify-send "hello notify"
$ notify-send "Title" "hello notify"
$ notify-send "Title" "hello notify" -u critical
$ notify-send "Title" "hello notify" -u low
$ notify-send "Title" "hello notify" -u normal -i error
$ notify-send "Title" "hello notify" -u normal
$ notify-send "Lazypic" "http://lazypic.org" -u normal
$ notify-send "Title" "hello notify" -u critical -i '/home/user/icon.png'
```

인스톨이 되면 알림을 주는 스크립트의 예
```bash
# yum -y install gimp && notify-send 'Install Complete' 'Your system install Gimp successfully!' -u normal -t 7500 -i checkbox-checked-symbolic
```

ssh 명령어를 이용해서 해당 서버에 notify-send 명령어를 실행하는 방법
```bash
ssh -X user@192.168.0.112 "DISPLAY=:0 notify-send 'Title' 'Body' -u critical -i face-worried'"
```

## macOS
macOS에는 osascript 명령을 이용할 수 있습니다.

```bash
$ osascript -e 'display notification "body" with title "Title"'
```
