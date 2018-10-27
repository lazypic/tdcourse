# install gcc

- CentOS7.5에서 yum 을 통해서 설치하는  gcc 버전은 4.8.5 입니다.
```
$ tail /etc/redhat-release 
CentOS Linux release 7.5.1804 (Core)
# yum install gcc
```

- VFX platform 가이드에 맞추어서 개발하기 위해서는 gcc 6.3.1 버전으로 설치할 필요가 있습니다.
```
# yum install centos-release-scl
# yum install devtoolset-6
$ scl enable devtoolset-6 bash
$ gcc -v
gcc version 6.3.1 20170216 (Red Hat 6.3.1-3) (GCC)
```
