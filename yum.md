# Yum
Red Hat 리눅스 계열에서 사용하는 패키지 메니징 툴입니다.
이 툴을 이용해서 패키지를 검색, 설치, 삭제 할 수 있습니다.

### EPEL
CentOS7을 설치하더라도 yum 명령어를 통해서 패키지를 설치할 때,
원하는 결과가 나오지 않는다.
EPEL(Extra Packages for Enterprise Linux) 리포지터를 추가하면 많은 패키지를 지원한다.

```
# yum install epel-release
```

### 검색

```
# yum search git
```

### 설치
```
# yum install git
```

### 업데이트
```
# yum update git
# yum update # 전체 패키지에 대해서 수행합니다. 오래걸립니다.
```

### 삭제
```
# yum remove git
```


