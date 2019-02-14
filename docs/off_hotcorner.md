# 핫코너 비활성화
CentOS 왼쪽 상단에 마우스를 가져가면 응용프로그램을 실행할 수 있는 핫코너가 열립니다.
그래픽툴을 사용할 때 Hot Corner 기능이 계속 켜지면서 불편할 때가 있습니다.
앞으로 뉴크를 많이 다루게 되니 Hot Corner 기능을 비활성화 해보겠습니다.

```
# yum -y install gnome-tweak-tool
# yum -y install gnome-shell-extension-no-hot-corner
# reboot
```

No topleft hot corner 기능을 끕니다.
```
$ gnome-tweaks
```

![off_hotcorner](../figures/off_hotcorner.png)

## 실습
-  최초 CentOS 설치시 핫코너 비활성화를 위한 패키지를 미리 설치할 수 있도록 스크립트를 추가합니다.
- .sh 스크립트를 github에 올립니다.
