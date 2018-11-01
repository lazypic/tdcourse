# 알람

### wall
```
$ echo "hello terminal notify" | wall
```

#### CentOS / notify-send

```
$ notify-send "hello notify"
$ notify-send "Title" "hello notify"
$ notify-send "Title" "hello notify" -u critical
$ notify-send "Title" "hello notify" -u low
$ notify-send "Title" "hello notify" -u normal -t 10000 -i error
$ notify-send "Title" "hello notify" -u critical -i '/home/user/icon.png'
```


인스톨 스크립트 만들기
```
yum -y install gimp && notify-send 'Install Complete' 'Your system install Gimp successfully!' -u normal -t 7500 -i checkbox-checked-symbolic
```

ssh 명령어를 이용해서 해당 서버에 notify-send 날리기
```
ssh -X user@192.168.0.112 "DISPLAY=:0 notify-send 'Title' 'Body' -u critical -i face-worried'
```

#### macOS
macOS에는 osascript 명령을 이용할 수 있다.

```
$ osascript -e 'display notification "body" with title "Title"'
```
