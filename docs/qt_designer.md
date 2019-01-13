# Qt5 Designer 설치
인터페이스를 간단하게 만들 수 있도록 개발자를 도와주는 툴입니다.

## 리눅스
프로그램 > 즐겨찾기 > 응용프로그램 설치 > Qt5 Designer 설치

## macOS
- https://www.anaconda.com/download 를 설치합니다.
bin폴더에 Designer.app 파일이 있습니다. 실행합니다.

물리적인 위치는 아래와 같습니다.
```
~/anaconda2/bin/Designer.app/Contents/MacOS
```

anaconda가 설치되면 ~/.bash_profile 파일에 아래줄이 추가됩니다. 참고하세요.
```
# added by Anaconda2 5.3.1 installer
# >>> conda init >>>
# !! Contents within this block are managed by 'conda init' !!
__conda_setup="$(CONDA_REPORT_ERRORS=false '/Users/woong/anaconda2/bin/conda' shell.bash hook 2> /dev/null)"
if [ $? -eq 0 ]; then
    \eval "$__conda_setup"
else
    if [ -f "/Users/woong/anaconda2/etc/profile.d/conda.sh" ]; then
        . "/Users/woong/anaconda2/etc/profile.d/conda.sh"
        CONDA_CHANGEPS1=false conda activate base
    else
        \export PATH="/Users/woong/anaconda2/bin:$PATH"
    fi
fi
unset __conda_setup
```

Designer 만 사용한다면 위 설정 내용을 ~/.bash_profile에서 제거해주세요.


## 실습
- QT 디자이너를 이용해서 간단하게 인터페이스를 만들어 보겠습니다.
- .ui 파일로 저장하는 방법을 알아봅니다.
- 천천히 어떤 기능을 만들기 고민하고 아이디어를 스케치할 것