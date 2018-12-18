# 뉴크 Cmd
뉴크를 터미널에서 commandline으로 조작하는 방법을 알아보겠습니다.

## 뉴크 실행
터미널을 이용해서 뉴크를 실행해보겠습니다.

```
$ cd Nuke11.2v5
$ ./Nuke11.2
```

NukeX 실행
```
$ cd Nuke11.2v5
$ ./Nuke11.2 --nukex
```

Nuke Studio 실행
```
$ cd Nuke11.2v5
$ ./Nuke11.2 --studio
```

## 뉴크 렌더링
자주 사용하는 렌더링 패턴

```bash
$ nuke -F 30-50 -x myscript.nk
```

```bash
$ nuke -F 30-50 -X WritenodeName myscript.nk
```

`-i` 옵션은 라이센스와 관련되어 있습니다.
```
-i
```

`-m` 사용할 쓰레드

`-f` full 레졸루션으로 열기 `-p` 프록시 레졸루션으로 열기. 요즘처럼 4K를 작업하는 상황에서는 많이 사용합니다.

`--sro` 렌더 Order 순서대로 렌더링 합니다.

`-remap` 경로를 바꾸어서 렌더링.

cat imageconvertwithargs.py
```python
import sys
r = nuke.nodes.Read(file = sys.argv[1])
w = nuke.nodes.Write(file = sys.argv[2])
w.setInput(0, r)
nuke.execute("Write1", 1, 5)
```
 
```bash
$ nuke -t imageconvertwithargs.py myimage.####.tif myimage.####.jpg
```

#### Reference
- https://learn.foundry.com/nuke/8.0/content/user_guide/configuring_nuke/command_line_operations.html

## 실습
- 한 폴더에 모여있는 뉴크파일을 렌더링 하는 스크립트를 python으로 작성해보세요.