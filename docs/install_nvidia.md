# 그래픽카드 드라이버 셋팅

Nvidia 그래픽카드 드라이버를 설치해보겠습니다.

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