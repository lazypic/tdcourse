# NDK
뉴크는 C++을 이용해서 노드를 개발 할 수 있습니다.

## 상용플러그인의 예
- https://www.videocopilot.net/products/opticalflaresNuke/

## 예제 컴파일하기
뉴크를 설치하면 C++ 예제 코드는 아래 경로에 존재합니다.

```
Documentation/NDK/examples
```

위 경로에서 아래 명령어를 실행해보세요.
```
$ make
```

g++-4.8 명령어를 찾을 수 없다고 나오면 Makefile을 편집하여 `g++-4.8` 부분을 `g++`로 변경해주세요. CentOS7.5의 기본 g++ 버전은 `4.8.5`입니다.

컴파일이 끝나면 같은 경로에 .so 파일이 생성됩니다.

## Reference
- https://learn.foundry.com/nuke/developers/63/ndkdevguide