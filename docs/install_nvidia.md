# 그래픽카드 드라이버 셋팅

Nvidia 그래픽카드 드라이버를 설치해보겠습니다.

- A클래스의 강의실 그래픽 카드는 Nvidia Quadro K2200 입니다.
- B클래스의 강의실 그래픽 카드는 Nvidia Quadro M4000 입니다.

그래픽 드라이버를 체크하겠습니다.

```bash
$ su
#  lshw -numeric -C display
```
driver 부분이 `driver=nouveau` 로 잡혀있는지 체크합니다.

```bash
$ su
# yum update
# yum install kernel-devel
# yum install kernel-headers
# yum install gcc make
```

```bash
# uname -r
# rpm -q kernel-devel
```
중요 : 위 명령어를 타이핑 했을 때 무조껀 버전이 같아야 합니다.
버전이 같지 않다면 재부팅하고 버전이 같을 때까지 반복하여 맞추어주세요.


드라이버를 다운로드 합니다.
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

```
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