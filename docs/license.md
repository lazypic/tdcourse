# 뉴크 라이센스 셋팅

## Windows10에서 맥 어드레스 알아내는 방법
`WindowKey + R > cmd 입력후 Enter` 키를 이용해서 터미널을 띄웁니다.

아래 명령어를 타이핑 하면 맥어드레스를 알아낼 수 있습니다.
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

벤더사에서 보내준 이메일내부에 FoundryLicenseKeys.zip 파일을 다운로드 받습니다.
```
$ cd ~/Download
$ unzip FoundryLicenseKeys.zip
# FoundryLicenseUtility -l ~/Downloads/FoundryLicenseKeys/foundry.lic
```

뉴크가 정상적으로 실행되는지 체크합니다.

## 뉴크 다운로드 및 설치
foundry.com에 가입을 해야 제품을 다운로드 할 수 있습니다.

http://foundry.com/products/nuke/download 를 클릭하고 로그인해서 제품을 다운로드 받으세요.

```
$ cd ~/Download
$ tar -xvf Nuke11.2v5-linux-x86-release-64.tgz
$ ./Nuke11.2v5-linux-x86-release-64-installer
```
관리자 계정으로 뉴크를 설치하지 않았습니다. 사용자로 설치하게 되면 뉴크는 `~/Nuke11.2v5` 폴더에 설치됩니다.