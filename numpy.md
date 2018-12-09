# Numpy
파이썬에 빠른 수치연산을 처리할 때 사용합니다.
내부는 실제로 C 또는 Fortran 으로 작성되어있기 때문에 굉장히 빠릅니다.

![fortran](https://image.slidesharecdn.com/20161030pythonatwarpspeed-4zu3-161115155137/95/python-at-warp-speed-13-638.jpg?cb=1479225194)

우리가 사용하는 라이브러리, 프로그램 내부에서 Numpy를 접하기도 하고 자주 사용됩니다. 설치해줍니다.

## 설치방법

먼저 [pip를 설치](pip.md)합니다.

```
# pip install numpy
```

#### Reference
그래프에 보면 Cython의 퍼포먼스가 더 좋다는 것을 알 수 있습니다. 여러분의 파이썬 코드를 cython을 이용해서 .so 파일로  컴파일하면 속도를 올릴 수 있습니다. 만약 Cython도 추후 설치하고 싶다면, 아래처럼 설치해주세요.

```
# pip install Cython
```
- https://cython.readthedocs.io/en/latest/src/tutorial/cython_tutorial.html