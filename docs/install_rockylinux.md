# install RockyLinux

RockyLinux 8.9을 설치해보겠습니다.

## 이미지 다운로드

- Rockylinux 이미지를 다운로드 받습니다.
- https://rockylinux.org
- 강의실에서는 다른 수업의 경우 윈도우로 진행하기 때문에 리눅스 설치시 멀티 부팅을 할 수 있도록 설치합니다.
- 강의실 Root 패스워드는 추후 관리를 위해서 `imroot`로 통일해주세요.
- 강의실에서 부팅을 USB로 하기 위해서는 Bios 패스워드가 필요합니다.

## 부팅 USB 만들기

#### .iso to USB (windows)
![rufus](https://user-images.githubusercontent.com/1149996/49558884-04524300-f950-11e8-833e-2b9e6d7a1fce.png)

윈도우즈에서 리눅스 부팅 usb를 제작하기 위해서는 rufus 유틸리티가 필요합니다. 아래 링크에서 다운로드 합니다.
- https://rufus.ie/ko_KR.html

#### .iso to USB (linux)

USB 장치를 검색합니다.

```bash
lsblk
sudo umount /dev/sdc1
```

USB 이미지를 굽습니다.

```bash
sudo dd if=/home/jason/Downloads/Rocky-8.9-x86_64-dvd1.iso of=/dev/sdc bs=4M status=progress && sync
```

#### .iso to USB (macOS)
- 다운받은 .iso파일을 .img로 바꾸어줘야하는 작업이 필요합니다.

```bash
$ hdiutil convert -format UDRW -o ~/Downloads/Rocky-8.9-x86_64-dvd1.img ~/Downloads/Rocky-8.9-x86_64-dvd1.iso
```

- 변환된 파일은 .dmg 확장자가 붙습니다. mv명령어를 통해서 제거합니다.

```bash
$ mv ~/Downloads/Rocky-8.9-x86_64-dvd1.img.dmg ~/Downloads/Rocky-8.9-x86_64-dvd1.img
```

- USB의 이름을 확인합니다.

```bash
$ diskutil list
```

- 제 컴퓨터에서는 disk2 로 출력되었습니다. 컴퓨터마다 다를 수 있습니다. dd 옵션뒤에는 절대경로가 들어가야 합니다.

```bash
$ sudo umount /dev/disk4
$ sudo diskutil unmountDisk disk4 # 만약 Resource busy가 뜨면 타이핑해주세요.
$ sudo dd if=/Users/woong/Downloads/Rocky-8.9-x86_64-dvd1.img of=/dev/rdisk4 bs=1m
```

- 잘 진행이 되면 아래 메시지를 출력후 종료됩니다.

```bash
13097+1 records in
13097+1 records out
13733806080 bytes transferred in 584.376422 secs (23501643 bytes/sec)
```

- USB를 추출합니다.

```bash
$ diskutil eject /dev/disk4
Disk /dev/disk4 ejected
```


## Windows10

강의실에는 Windows10이 설치되어 있습니다.
Windows10이 깔려있는 하드디스크에 리눅스를 설치하는 것은 모팩아카데미와 측에서 권장하지 않습니다.
준비된 SSD 하드디스크를 시스템에 장착하고 리눅스 설치를 진행합니다.

## 리눅스 설치

- 준비물 : 하드디스크, CentOS USB 이미지를 준비합니다.
- 부팅시 F9를 눌러서 USB로 부팅할 수 있도록 해주세요. 바이오스 패스워드는 강의실에서 공유합니다.

![install_centos01](../figures/cent_install_01.png)

Test this media & install CentOS7을 선택합니다. 이미지가 문제가 없는지 체크하는 과정이 있습니다.

![install_centos02](../figures/cent_install_02.png)

언어를 선택합니다.

![install_centos03](../figures/cent_install_03.png)

소프트웨어 선택에 들어가서 GNOME 데스크탑을 선택합니다.

![install_centos04](../figures/cent_install_04.png)

설치 대상에서 설치할 하드디스크를 선택합니다.

![install_centos05](../figures/cent_install_05.png)

설치가 진행됩니다.
설치중에 Root 사용자, 일반 사용자의 계정을 만들 수 있습니다.

![install_centos06](../figures/cent_install_06.png)

루트 사용자 패스워드를 설정해주세요. 관리를 위해서 `imroot`로 입력해주세요.

![install_centos07](../figures/cent_install_07.png)

사용자 생성을 진행합니다. 자신이 사용할 이름과 패스워드를 설정해주세요.
사용자 통일을 위해서 `ec2-user` 라는 이름을 사용하겠습니다.
설치가 끝나면 재부팅을 하게 됩니다.

![install_centos08](../figures/cent_install_08.png)

재부팅 이후 라이센스 약관동의 창이 뜹니다.

## 바이오스 셋팅

1. F10을 눌러서 바이오스에 들어갑니다.
1. Storage > Boot Order
1. SSD 하드의 순서를 위로 올려줍니다.
1. F10을 눌러서 설정을 마칩니다.
1. File > Save Changes and Exit 를 눌러줍니다.

## Referenece

- http://www.advancedclustering.com/act_kb/installing-nvidia-drivers-rhel-centos-7
- http://thrillfighter.tistory.com/618
- http://eeingee.tistory.com/1
