# install gcc9

- CentOS 7.9에서 yum 을 통해서 설치하는  gcc 버전은 4.8.5 입니다.

```bash
$ tail /etc/redhat-release 
CentOS Linux release 7.5.1804 (Core)
$ sudo yum install gcc
```

- VFX Reference Platform 가이드에 맞추어서 개발하기 위해서는 gcc 9.x 버전으로 설치할 필요가 있습니다.

```bash
$ sudo yum install centos-release-scl-rh
$ sudo yum --enablerepo=centos-sclo-rh-testing install devtoolset-9
$ scl enable devtoolset-9 bash
$ gcc -v
gcc version 6.3.1 20170216 (Red Hat 6.3.1-3) (GCC)
```
