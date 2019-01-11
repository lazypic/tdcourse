# trans 설치
trans는 제가 Go 언어를 이용해서 만든 터미널 번역기 입니다.

프로젝트 리포지터리 : https://github.com/lazypic/trans

기술적으로 특별한 기능은 없으며, 언어인식 라이브러리와 카카오 AI 번역기의 웹 API를 연결하여 간단하게 터미널에서 사용가능하도록 만들어봤습니다. 설치도 단순한 구조입니다.

한국으로 들어오는 VFX 업무중 많은 분량은 중국에서 넘어옵니다. 간혹 업무를 하다가 중국어를 잘 모르겠거나, 간단하게 번역업무를 할 때 활용합니다.

이번 시간에는 trans라고 하는 명령어를 자동 설치하는 .sh 파일을 제작하고 구동시켜볼 예정입니다.

```bash
$ echo $PATH
```

위 경로에 실행파일이 존재하면 실행파일을 인식하여 터미널에서 명령어를 사용할 수 있습니다.
위 특징 때문에 우리는 trans 명령어를 `~/bin` 폴더에 설치할 것입니다.

```bash
$ cd ~
$ mkdir bin
$ cd bin
$ wget https://github.com/lazypic/trans/releases/download/v0.1/trans_linux.tgz
$ tar -zxvf trans_linux.tgz
$ rm trans_linux.tgz
```

## 실습
- 위 형태를 .sh 파일로 만들어서 설치 스크립트를 만들어 보겠습니다.
- 응용 : 위 형태의 .sh 파일을 잘 만들 수 있다면 여러분이 강의를 통해서 배우는 모든 설치작업을 자동화 스크립트로 바꿀 수 있습니다.
