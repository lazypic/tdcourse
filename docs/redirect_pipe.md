# Redirect, Pipe
리눅스에서 자주 사용하는 리다이렉트와 파이프에 대해서 설명하겠습니다.

## Redirect
명령어의 입력이나 출력을 파일로 사용할 때 사용합니다.
이 특징을 이용하면 특별한 명령어 없이 리다이렉트만을 이용해서 로그서비스를 만들 수 있습니다.

- `>` 문자는 결과를 파일로 전송합니다. 이미 파일이 존재할 때는 원본 파일을 덮어쓰기 합니다. 주의합시다.
```
$ ls -al > ~/ls.txt
$ head < ~/ls.txt
$ head < ~/ls.txt > ls_and_head.txt
```

- `>>` 문자는 파일이 존재하는 경우 맨 아랫줄에 정보를 추가합니다.
```
$ ls -al > ~/ls.txt
$ echo "add line" >> ~/ls.txt
$ cat ~/ls.txt
```

## Pipe
`A | B` A 명령어의 출력을 B 명령어의 입력으로 사용해야할 때 파이프를 사용합니다.

- cowsay 명령어를 설치하고 파이프를 테스트해보는 예제.
```
$ su
# yum install epel-release
# yum install cowsay
# exit
$ echo "hello Linux" | cowsay
$ echo "hello CentOS" | cowthink
```

#### 응용 : 폴더안의 파일 갯수 세기
```
$ ls | wc -l
```
