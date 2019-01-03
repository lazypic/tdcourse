# 뉴크 라이센스 셋팅

홈페이지를 통해서 뉴크를 설치하면 1달간 라이센스를 사용할 수 있습니다.
PLE 모드는 무료로 사용할 수 있습니다.

# 정품 라이센스 설치법

## Windows10에서 맥 어드레스 알아내는 방법
`WindowKey + R > cmd 입력후 Enter` 키를 이용해서 터미널을 띄웁니다.

아래 명령어를 타이핑 하면 맥 어드레스를 알아낼 수 있습니다.
```
> getmac /v
```

## CentOS7에서 맥 어드레스를 알아내는 방법
뉴크 라이센스를 발급받기 위해서는 먼저 맥 어드레스를 소프트웨어 판매자에게 알려줘야 합니다.

터미널에서 아래처럼 타이핑합니다.
```
$ cat /sys/class/net/*/address
```

결과의 예시는 아래처럼 나옵니다.

```
00:1f:16:20:56:e6
52:54:00:17:16:e9
00:00:00:00:00:00
```

## 뉴크 노드락 라이센스 셋팅
Foundry License Utility(FLU)를 다운로드 받습니다.
- https://www.foundry.com/licensing?_ga=2.38553443.1364747009.1544115508-920726775.1531228820

```bash
$ cd ~/app
$ wget https://s3.amazonaws.com/thefoundry/tools/FLU/7.3v2/FLU_7.3v2_linux-x86-release-64RH.tgz
$ tar -xvf FLU_7.3v2_linux-x86-release-64RH.tgz
$ cd FLT_7.3v2_linux-x86-release-64RH
$ ./FoundryLicenseUtility -i
System ID : 001f162056e0 #mac address가 출력됩니다. 이 정보를 벤더사에 보내주세요.
```

라이센스 요청이 받아들여지면 벤더사에서 이메일을 보내줍니다. 첨부파일에는  FoundryLicenseKeys.zip 라이센스 파일이 존재하게됩니다.
```
$ cd ~/Download
$ unzip FoundryLicenseKeys.zip
# ~/app/FoundryLicenseUtility -l ~/Downloads/FoundryLicenseKeys/foundry.lic
```

뉴크 또는 Foundry 제품이 정상적으로 잘 실행되는지 체크합니다.