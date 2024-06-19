# 그래픽카드 드라이버 셋팅

많이 사용하는 Nvidia 그래픽카드 드라이버를 설치해보겠습니다.

- A클래스의 강의실 그래픽 카드는 Nvidia Quadro K2200 입니다.
- B클래스의 강의실 그래픽 카드는 Nvidia Quadro M4000 입니다.

그래픽카드로 현재 사용중인 드라이버를 체크해보겠습니다.

```bash
$ su
#  lshw -numeric -C display
```

driver 부분이 `driver=nouveau` 로 잡혀있는지 체크합니다.

## nouveau란?

nouveau(누브~) 프랑스어로 `처음부터, 새롭게 다시..`라는 뜻을 가진 단어입니다.
[nouveau](https://nouveau.freedesktop.org/wiki/)프로젝트는 NVIDIA 그래픽 카드용 오픈소스 드라이버입니다. 기본적인 리눅스를 사용할 때는 nouveau 드라이버로 충분하지만 전문적인 그래픽작업을 할 때는 그래픽카드의 부가적인 기능들이 필요합니다. 안타깝게도 NVIDIA 드라이버는 폐쇄소스 코드라서 그래픽카드의 부가적인 기능을 사용하기 위해서는 정식 드라이버를 설치해야 한답니다.

> nvidia가 안드로이드등 리눅스 부문에서 돈을 벌면서, 지적재산권 보호를 위해 오픈소스 드라이버를 위한 정보를 제공하지 않는다는 이유 생긴 사소한 사건. - 49분 59초 : https://www.youtube.com/watch?v=MShbP3OpASA

## 설치

그래픽카드 드라이버를 설치하기 위해서는 yum 업데이트 및 아래 도구가 필요합니다.

```bash
$ su
# dnf update
# dnf install kernel-devel
# dnf install kernel-headers
# dnf install gcc make
```

```bash
# uname -r
# rpm -q kernel-devel
```

중요 : 위 명령어를 타이핑 했을 때 무조껀 버전이 같아야 합니다.
버전이 같지 않다면 재부팅하고 버전이 같을 때까지 반복하여 맞추어주세요.

강의실 조건에 맞는 드라이버를 다운로드 합니다.
http://www.nvidia.com/drivers

```bash
# cd ~
# wget http://kr.download.nvidia.com/XFree86/Linux-x86_64/410.78/NVIDIA-Linux-x86_64-410.78.run
```

grub 설정파일이 있는 곳으로 이동후 설정파일을 백업하고 편집합니다.

```bash
# cd /etc/default
# cp grub grub.bak
# vim grub
```

내용 내용처럼 변경합니다. 6번째 줄만 변경해주세요.

```bash
1: GRUB_TIMEOUT=5
2: GRUB_DISTRIBUTOR="$(sed 's, release .*$,,g' /etc/system-release)"
3: GRUB_DEFAULT=saved
4: GRUB_DISABLE_SUBMENU=true
5: GRUB_TERMINAL_OUTPUT="console"
6: GRUB_CMDLINE_LINUX="crashkernel=auto rhgb quiet nouveau.modeset=0"
7: GRUB_DISABLE_RECOVERY="true"
```

```bash
# grub2-mkconfig -o /boot/grub2/grub.cfg
# grub2-mkconfig -o /boot/efi/EFI/centos/grub.cfg
```

재부팅합니다.

```bash
# reboot
```

nouveau가 설정되지 않았기 때문에 GNOME 데스크탑 접근시 화면이 깨질 수 있습니다.
화면이 깨진다면 `Ctrl + Alt + F2` 키를 눌러서 콘솔접근을 해주세요.

```bash
#  lshw -numeric -C display
```

`driver=nouveau` 부분이 사라져 있는지 체크합니다.

그래픽카드 드라이버를 설치하기 위해서는 Xorg server를 중지해야합니다.

```bash
# systemctl isolate multi-user.target
```

```bash
# cd ~
# bash ./NVIDIA-Linux-x86_64-410.78.run
# reboot
```

잘 설치가 되었다면 GNOME 데스크탑 터미널에서 아래처럼 타이핑해서 설정창이 잘 뜨는지 체크합니다.

```bash
$ nvidia-settings
```

## Reference

https://linuxconfig.org/how-to-install-the-nvidia-drivers-on-centos-7-linux
