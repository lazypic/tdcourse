# pip
파이썬 패키지 관리툴입니다.
앞으로 파이썬 및 기타 라이브러리를 이용해서 프로그래밍 할 상황이 많이 발생합니다.
자주 사용하는 파이썬 라이브러리를 설치할 때 pip 명령어는 굉장히 편리합니다.

- 홈페이지 : https://pypi.org

## 설치
```
$ curl "https://bootstrap.pypa.io/get-pip.py" -o "get-pip.py"
# python get-pip.py
```

## 라이브러리 설치경로
시스템이 엉키지 않도록 pip 설치시 --user 옵션을 사용합니다.

```bash
$ pip install --user numpy
```

설치되는 경로는 ~/.local 폴더 입니다.

```
~/.local/lib/python2.7/site-packages
```

## 실습
- pip를 자동으로 설치하는 `pip.sh` 스크립트를 작성하고 Github에 git push 합니다.

## Reference
- 설치 원문 : https://pip.pypa.io/en/stable/installing/
