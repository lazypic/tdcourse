# install CentOS
- centOS 이미지를 다운로드 받습니다.
- https://www.centos.org/download/
- CentOS를 사용하는 이유 : https://www.foundry.com/products/nuke/requirements
- 강의실에서는 다른 수업의 경우 윈도우로 진행하기 때문에 리눅스 설치시 멀티 부팅을 할 수 있도록 설치합니다.
- 강의실 Root 패스워드는 추후 관리를 위해서 `I'm_groot!`로 통일해주세요.

## USB 만들기

#### .iso to USB (windows)
![rufus](https://user-images.githubusercontent.com/1149996/49558884-04524300-f950-11e8-833e-2b9e6d7a1fce.png)

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

- 제 컴퓨터에서는 disk2 로 출력되었습니다. 컴퓨터마다 다를 수 있습니다.

```
$ sudo umount /dev/disk2
$ sudo diskutil unmountDisk disk3 # 만약 Resource busy가 뜨면 타이핑해주세요.
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

## 멀티부팅 with Windows
#### Windows10 설치
이미 강의실에는 Windows10이 설치되어 있습니다.
Windows10이 깔려있는 곳에 리눅스를 설치하는 것은 모팩아카데미와 측에서 권장하지 않습니다.
하드디스크를 하나 준비하여 시스템에 붙히고 리눅스를 설치하기로 했습니다.

#### CentOS 설치
- 준비물 : 하드디스크, CentOS USB 이미지를 준비합니다.
- 부팅시 F12를 눌러서 USB로 부팅할 수 있도록 해주세요. 바이오스 패스워드는 강의실에서 공유합니다.

#### Grub2 설정


#### Reference
- http://thrillfighter.tistory.com/618
- http://eeingee.tistory.com/1
- 검색 -> 컴퓨터관리

## 그래픽카드 드라이버 셋팅
- A클래스의 강의실 그래픽 카드는 Nvidia Quadro K2200 입니다.
- B클래스의 강의실 그래픽 카드는 Nvidia Quadro M4000 입니다.

```
yum update
yum groupinstall "GNOME Desktop" "Development Tools"
yum install kernel-devel
yum install epel-release
yum install dkms
```

드라이버를 다운로드 합니다.
http://www.nvidia.com/object/unix.html

$ vim /etc/default/grub. Append the following to "GRUB_CMDLINE_LINUX"
rd.driver.blacklist=nouveau nouveau.modeset=0

```
# grub2-mkconfig -o /boot/grub2/grub.cfg
```

/etc/modprobe.d/blacklist.conf 파일에 아래 내용을 추가합니다.

```
blacklist nouveau
```

과거 initramfs를 백업하고 새로 운 파일을 생성합니다.
```
# mv /boot/initramfs-$(uname-r).img /boot/initramfs-$(uname -r)-nouveau.img
# dracut /boot/initramfs-$(uname -r).img $(uname -r)
```

재부팅합니다.

```
# systemctl isolate multi-user.target
# sh NVIDIA-Linux-x86_64-*.run
```

재부팅을 다시 합니다.


#### Referenece
http://www.advancedclustering.com/act_kb/installing-nvidia-drivers-rhel-centos-7