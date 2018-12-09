# Redirect, Pipe

## Redirect
명령어의 입력이나 출력을 파일로 사용할 때 사용합니다.

- `>` 문자는 결과를 파일로 전송합니다. 이미 파일이 존재할 때는 파일을 덮어쓰기 합니다. 주의합니다.
```
$ ls -al > ~/ls.txt
$ head < ~/ls.txt
$ head < ~/ls.txt > ls_and_head.txt
```

- `>>` 문자는는 파일이 존재하는 경우 맨 아랫줄에 정보를 추가합니다.
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
# yum install cowsay
# exit
$ echo "hello Linux" | cowsay
$ echo "hello CentOS" | cowthink
```
