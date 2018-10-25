# install CentOS
- centOS 이미지를 다운로드 받습니다.
- https://www.centos.org/download/
- CentOS를 사용하는 이유 : https://www.foundry.com/products/nuke/requirements

#### .iso to USB (windows)
- https://rufus.ie/ko_KR.html

#### .iso to USB (macOS)
- 다운받은 .iso파일을 .img로 바꾸어줘야하는 작업이 필요합니다.
```
$ hdiutil convert -format UDRW -o ~/Downloads/CentOS-7-x86_64-Everything-1804.img ~/Downloads/CentOS-7-x86_64-Everything-1804.iso
```

- 변환된 파일은 .dmg 확장자가 붙습니다. mv명령어를 통해서 제거합니다.
```
$ mv ~/Downloads/CentOS-7-x86_64-Everything-1804.img.dmg ~/Downloads/CentOS-7-x86_64-Everything-1804.img
```

- USB의 이름을 확인합니다.
```
$ diskutil list
```

- 내 컴퓨터에서는 disk2 로 출력되었습니다.

```
$ sudo umount /dev/disk2
$ sudo dd if=~/Downloads/CentOS-7-x86_64-Everything-1804.img of=/dev/rdisk2 bs=1m
```
- 잘 진행이 되면 아래 메시지를 출력후 종료됩니다.
```
8961+1 records in
8961+1 records out
9396461568 bytes transferred in 706.427948 secs (13301373 bytes/sec)
```

- USB를 추출합니다.
```
$ diskutil eject /dev/disk2
Disk /dev/disk2 ejected
```

#### 멀티부팅 with Windows
- http://thrillfighter.tistory.com/618
- http://eeingee.tistory.com/1
- 검색 -> 컴퓨터관리
