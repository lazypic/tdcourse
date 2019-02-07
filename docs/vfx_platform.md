# VFX Reference Platform
VFX 시장에서 툴과 라이브러리를 툴 제작사가 개발시 수많은 언어, 라이브러리를 사용합니다.
회사, 개발자, 각 회사들의 인하우스 개발등.. 사용 언어와 라이브러리의 버전을 약속하기 위한 제안규칙이라고 생각해주세요.

홈페이지 : https://www.vfxplatform.com

라이브러리 버전을 공유하고 제안하는 이유
- 다른 소프트웨어들 끼리 호환되지 않는 문제를 최소화
- 리눅스 파이프라인을 지원할 때 드는 비용을 감소
- 각 회사에 리눅스 파이프라인 채택을 장려

VFX Refercene Platform 규칙은 [Visual Effects Society Technology Committee](https://www.visualeffectssociety.com/ves-committees?jump-9)에서 회의를 통해 매년 업데이트합니다. 이 규칙은 Foundry등 툴 제작사가 따르고 있습니다.

Visual Effects Society Technology Commitee 에 들어가면 각 위원회 리스트가 나옵니다.
여러분도 같이 참여하고 싶다면 Chairs 항목에 있는 의장에게 메일을 보내서 각 위원회에 참여하고 싶다고 의사를 밝히면 됩니다.

그래픽툴을 제작하는 회사가 그래픽스 제품을 출시후 VFX Reference Platform 몇년도 버전을 따르고 있는지 정보를 공표합니다.
- 예) Nuke & Hiero : https://www.foundry.com/news-awards/nuke-hiero-11-release
- 예) Katana : https://www.foundry.com/products/katana/new-releases
- 예) Houdini의 움직임 : http://www.sidefx.com/docs/houdini/licenses/index

자신이 하는 프로젝트에 따라서 버전을 맞추기 위해 홈페이지를 통해서 소스코드를 다운받아서 사용해는것이 좋을 수 있습니다.

## Gcc
GNU Compiler Collection의 약자.
여러 컴파일러의 모음입니다. 지원하는 컴파일 언어는 C, C++, Objective-C, Fortran, Ada, Go입니다.

CentOS7.6 에서 yum 을 통해서 설치하는  gcc 버전은 4.8.5 입니다.

```bash
$ tail /etc/redhat-release 
CentOS Linux release 7.5.1804 (Core)
# yum install gcc
$ gcc -v
gcc version 4.8.5 20150623 (Red Hat 4.8.5-28) (GCC)
```

VFX Reference Platform 가이드에 맞추어서 개발하기 위해서는 gcc 6.3.1 버전으로 설치할 필요가 있습니다.

아래형태로 gcc를 설치해주세요.

```bash
# yum install centos-release-scl
# yum install devtoolset-6
$ scl enable devtoolset-6 bash
$ gcc -v
gcc version 6.3.1 20170216 (Red Hat 6.3.1-3) (GCC)
```

VFX Reference Platform 권장 버전역시 6.3.1 입니다.

devtoolset-6의 설치 위치는 `/opt/rh/devtoolset-6` 입니다.


## Glibc
The GNU C Library 입니다. VFX Reference Platform 권장버전은 2.17입니다.

#### 설치
```
# yum install glibc
```

리눅스에서 버전을 확인하는 방법
```
$ getconf -a | grep glibc
GNU_LIBC_VERSION                   glibc 2.17
```

## Python
파이썬 버전확인 방법
```
$ python --version
Python 2.7.5
```

## Qt
버전확인 방법
```
$ qtdiag
Qt 5.9.2 (x86_64-little_endian-lp64 shared (dynamic) release build; by GCC 4.8.5 20150623 (Red Hat 4.8.5-28)) on "xcb" 
```

## PyQt5
python3으로 올리고 설치해주세요. 대부분의 VFX 툴은 아직 Python2.7.x 를 사용합니다.
VFX툴을 개발 한다면, PySide2 사용을 추천합니다.

## PySide
설치
```bash
$ pip install --user PySide2
```

버전체크

```bash
$ python
>>> import PySide2
>>> print PySide2.__version__
5.11.2

```

잘 작동된다면 아래 코드를 타이핑후 실행해보세요.

pyside2_test.py

```python
import sys
from PySide2 import QtWidgets


app = QtWidgets.QApplication(sys.argv)

hello = QtWidgets.QPushButton("Hello PySide2")
hello.resize(100, 30)

hello.show()

sys.exit(app.exec_())
```

```
$ python pyside2_test.py
```

## NumPy
```bash
# pip install --user numpy
```

버전확인
```bash
python
>>> import numpy
>>> print numpy.__version__
1.7.1
```

## [OpenEXR](openexr.md)

## [Ptex](ptex.md)

## [OpenSubdiv](opensubdiv.md)

## [OpenVDB](openvdb.md)

## [Alembic](alembic.md)

## [OpenColorIO](opencolorio.md)

## FBX
FBX는 Autodesk에서 개발하는 포멧입니다. 리눅스에서는 SDK를 받아서 사용할 수 있습니다. 개발자를 위한 SDK만 지원하고 소스를 지원하지는 않습니다.
- https://www.autodesk.com/developer-network/platform-technologies/fbx-sdk-2019-2

## Boost
자신이 직접 컴파일해서 사용한다면 버전을 정확하게 알 수 있지만,
회사에 이미 누군가가 셋팅해서 사용한다면 간단하게 cpp 코드를 짜서 버전을 알아낼 수 있습니다.

```cpp
#include <boost/version.hpp>
#include <iostream>

using namespace std;

int main()
{
    cout << "Boost version: " << BOOST_LIB_VERSION << endl;
    return 0;
}
```

윜 코드를 컴파일하고 실행하는 방법은 아래와 같습니다. CentOS7.6 기본 Boost는 1.53입니다.

```bash
$ g++ boost.cpp
$ ./a.out
Boost version: 1_53
```

## Intel TBB
Threading + Building Blocks의 약자입니다.
Intel 소프트웨어팀에서 개발한 병렬처리용 C++ 라이브러리.
병렬처리연산이 들어간 프로그램을 컴파일할 때 이 라이브러리가 사용될 확률이 높습니다.

#### 컴파일
```
$ cd ~/app
$ git clone https://github.com/01org/tbb tbb
$ cd tbb
$ make
```
- TBB_INSTALL_DIR = $HOME/tbb
- TBB_INCLUDE = $TBB_INSTALL_DIR/include
- TBB_LIBRARY_RELEASE = $TBB_INSTALL_DIR/build/linux_intel64_gcc_cc6.3.1_libc2.17_kernel3.10.0_release
- TBB_LIBRARY_DEBUG = $TBB_INSTALL_DIR/build/linux_intel64_gcc_cc6.3.1_libc2.17_kernel3.10.0_debug

Relese, Debug 폴더는 리눅스 커널마다 다를 수 있습니다.

#### Reference
- 예제 컴파일 문서 : https://github.com/01org/tbb/tree/tbb_2019/cmake

#### 읽어보기
- http://m.cafe.daum.net/betterspeed/8V7A/3?q=D_jDGwPlH16FY0&
- http://hootybaby.blogspot.com/2010/05/tbb.html

## Intel MKL
Intel Math Kernel Library의 약자입니다.
높은 성능이 필요한 과학, 공학, 금융쪽에서 사용할 수 있는 수학 라이브러리입니다.
소프트웨어 개발자가 이 라이브러리를 사용했다면 역시 필요한 라이브러리 입니다.

- 홈페이지 : https://software.intel.com/en-us/mkl
- 다운로드 : https://software.intel.com/en-us/mkl/choose-download/linux

#### Reference
https://software.intel.com/en-us/articles/intel-math-kernel-library-intel-mkl-2018-install-guide

#### 읽어보기
- http://www.sandia.co.kr/intelsw/performance_libraries/reseller_prodpage_mkl_and_mkl_cluster_edition.htm



## C++ API/SDK
VFX Reference Platform은 C++14 표준을 따릅니다.