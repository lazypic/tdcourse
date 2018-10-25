# install CentOS
- centOS 이미지를 다운로드 받습니다.
- https://www.centos.org/download/

#### ISO to USB / macOS
- 다운받은 .iso파일을 .img로 바꾸어줘야하는 작업이 필요합니다.
```
$ hdiutil convert -format UDRW -o ~/Downloads/CentOS-7-x86_64-Minimal-1804.img ~/Downloads/CentOS-7-x86_64-Minimal-1804.iso
```

- 변환된 파일은 .dmg 확장자가 붙습니다. mv명령어를 통해서 제거합니다.
```
$ mv ~/Downloads/CentOS-7-x86_64-Minimal-1804.img.dmg ~/Downloads/CentOS-7-x86_64-Minimal-1804.img
```

- USB의 이름을 확인합니다.
```
$ diskutil list
```

- 내 컴퓨터에서는 disk2 로 출력되었습니다.

```
$ sudo unmout /dev/disk2
$ sudo dd if=~/Downloads/CentOS-7-x86_64-Minimal-1804.img of=/dev/rdisk2 bs=1m
```
- 잘 진행이 되면 아래 메시지를 출력후 종료됩니다.
```
906+0 records in
906+0 records out
950009856 bytes transferred in 143.848588 secs (6604235 bytes/sec)
```

- USB를 추출합니다.
```
$ diskutil eject /dev/disk2
Disk /dev/disk2 ejected
```
