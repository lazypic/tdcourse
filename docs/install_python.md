# Install Python

Rocky Linux 8.5 에서 파이썬 설치를 다룹니다.
설치 이후 python 명령어를 타이핑하더라도 파이썬이 실행되지 않습니다.
update-alternavives 명령어를 이용해서 시스템에서 사용할 파이썬 버전을 설정해 주어야 합니다.

```bash
sudo dnf install python2 # python2.7을 설치합니다.
sudo dnf install python38 # python3.8을 설치합니다.
sudo dnf install python39 # python3.9를 설치합니다.
sudo update-alternatives --config python # 기본 파이썬 심볼릭링크 설정
```