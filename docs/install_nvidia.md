# 그래픽카드 드라이버 셋팅

Nvidia 그래픽카드 드라이버를 설치해보겠습니다.

- A클래스의 강의실 그래픽 카드는 Nvidia Quadro K2200 입니다.
- B클래스의 강의실 그래픽 카드는 Nvidia Quadro M4000 입니다.

그래픽 드라이버를 체크하겠습니다.
```
#  lshw -numeric -C display
```
driver 부분이 `driver=nouveau` 로 잡혀있는지 체크합니다.

```
$ su
# yum update
# yum install kernel-devel
# yum install kernel-headers
# yum install gcc make
```

```
# uname -r
# rpm -q kernel-devel
```
중요 : 위 명령어를 타이핑 했을 때 무조껀 버전이 같아야 합니다.
버전이 같지 않다면 재부팅하고 버전이 같을 때까지 반복하여 맞추어주세요.


드라이버를 다운로드 합니다.
http://www.nvidia.com/drivers

```
# wget http://kr.download.nvidia.com/XFree86/Linux-x86_64/410.78/NVIDIA-Linux-x86_64-410.78.run
```

grub 설정파일이 있는 곳으로 이동후 설정파일을 백업하고 편집합니다.
```
# cd /etc/default
# cp grub grub.bak
# vim grub
```

내용은 아래처럼 변경합니다.
```
GRUB_TIMEOUT=5
GRUB_DISTRIBUTOR="$(sed 's, release .*$,,g' /etc/system-release)"
GRUB_DEFAULT=saved
GRUB_DISABLE_SUBMENU=true
GRUB_TERMINAL_OUTPUT="console"
GRUB_CMDLINE_LINUX="crashkernel=auto rhgb quiet nouveau.modeset=0"
GRUB_DISABLE_RECOVERY="true"
```

```
# grub2-mkconfig -o /boot/grub2/grub.cfg
# grub2-mkconfig -o /boot/efi/EFI/centos/grub.cfg
```

재부팅합니다.
```
# reboot
```

만약 부팅이 되지 않으면 ctrl + alt + f2 키를 눌러서 콘솔접근을 해주세요.

```
#  lshw -numeric -C display
```

`driver=nouveau` 부분이 사라져 있는지 체크합니다.

드라이버를 설치하기 위해서는 Xorg server를 중지해야합니다.

```
# systemctl isolate multi-user.target
```


```
# bash ./NVIDIA-Linux-x86_64-410.78.run
```

잘 설치가 되었다면 터미널에서 아래처럼 타이핑해서 설정창이 잘 뜨는지 체크합니다.
```
$ nvidia-settings
```

## Reference
https://linuxconfig.org/how-to-install-the-nvidia-drivers-on-centos-7-linux