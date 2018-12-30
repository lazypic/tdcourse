# 파이썬 & ImageMagick
파이썬을 활용한 첫번째 실습입니다.

git 명령어를 이용하여 ~/example 파일을 다운로드 합니다.

```
$ cd ~
$ git clone http://github.com/cgiseminar/example
```

프로그래밍이 처음인 분을 위해서 쉽게 읽히도록 os.system 함수를 이용해서 코드를 작성해 보겠습니다.
os.system을 이용하면 터미널 창에서 입력한

```python
import os

p = "~/example/FOO_0010"
for f in os.listdir(p):
    os.system("convert %s.jpg %s.png" % (f,f))

4줄 선에서 이해가 갈수 있는 예제 작성할 것
```

## 제안
실무에서는 `os.system` 보다는 `subprocess`를 사용하는 것이 더 좋습니다. 명령어를 실행할 때 환경변수 및 STDIN, STDOUT, STDERR 처리를 할 수 있습니다.

## 실습
- 각 폴더마다 대표하는 이미지 썸네일을 한장 생성합니다.
- 썸네일을 생성할 때 중앙 프레임에 해당하는 이미지 썸네일을 생성하도록 코드를 리펙토링 해보세요.
- 