# Steam 설치
사람들이 리눅스를 기피하는 이유중 게임 엔터테인먼트를 즐기기 힘들다는 점이 있습니다.
스팀을 설치하면 리눅스에서 게임을 즐길 수 있습니다.

```
# yum-config-manager --add-repo=https://negativo17.org/repos/epel-steam.repo
# yum -y install steam
```

libva-intel-driver(x86-32)이 필요하다고 뜨면 아래줄을 입력해주세요.
```
# yum-config-manager --add-repo=http://negativo17.org/repos/epel-multimedia.repo
```

## Reference
- https://negativo17.org/steam/
