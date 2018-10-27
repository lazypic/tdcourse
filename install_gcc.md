# install gcc

- CentOS7.5의 gcc 버전은 4.8.5이다.
```
# yum install gcc
```

- VFX platform 가이드에 맞추어서 개발하기 위해서는 gcc 6.3.1 버전으로 올릴 필요가 있다.
```
# yum install centos-release-scl
# yum install devtoolset-6
$ scl enable devtoolset-6 bash
$ gcc -v
gcc version 6.3.1 20170216 (Red Hat 6.3.1-3) (GCC)
```
