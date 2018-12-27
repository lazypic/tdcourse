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
# yum groupinstall "GNOME Desktop" "Development Tools"
# yum install kernel-devel
# yum install kernel-headers
# yum install epel-release
# yum install dkms
```

드라이버를 다운로드 합니다.
http://www.nvidia.com/drivers

```
# wget http://kr.download.nvidia.com/XFree86/Linux-x86_64/410.78/NVIDIA-Linux-x86_64-410.78.run
```


vim /etc/default/grub
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

드라이버부분을 다시한번 체크해주세요.
접근이 되지 않으면 ctrl + alt + f2로 콘솔접근을 해주세요.
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

잘 설치가 되었다면 터미
```
$ nvidia-settings
```

nouveau 을 활성화시키면 충돌가능성이 있기에 blacklist해준다. 
```
# echo 'blacklist nouveau' >> /etc/modprobe.d/blacklist.conf
# dracut /boot/initramfs-$(uname -r).img $(uname -r) --force
# reboot
```

```
# wget http://kr.download.nvidia.com/XFree86/Linux-x86_64/410.78/NVIDIA-Linux-x86_64-410.78.run
```

```
# bash NVIDIA-Linux-x86_64-390.59.run
```

```
# nvidia-smi
```

```
$ vim /etc/default/grub. Append the following to "GRUB_CMDLINE_LINUX"
rd.driver.blacklist=nouveau nouveau.modeset=0
```

```
# grub2-mkconfig -o /boot/grub2/grub.cfg
```

/etc/modprobe.d/blacklist.conf 파일에 아래 내용을 추가합니다.

```
blacklist nouveau
```

과거 initramfs를 백업하고 새로운 파일을 생성합니다.
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


## Reference
https://linuxconfig.org/how-to-install-the-nvidia-drivers-on-centos-7-linux