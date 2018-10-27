# 리눅스 명령어

### ls
현재경로의 파일을 출력하는 명령어.

- 모든 파일(숨김파일포함)을 출력하며 list 형태로 출력하는 방법
```
$ ls -al
```

- 현재경로의 exr 파일을 출력.
```
$ ls *.exr
```

- 현재경로에서 1000 프레임의 시퀀스만 검색
```
$ ls filename.1???.exr
```

### . / ..
`.` 문자는 현재경로라는 뜻을 가진 문자입니다.
`..` 문자는 상위경로라는 뜻을 가진 문자입니다.
리눅스의 모든 경로는 언제나 현재경로와 상위 경로를 가지기 때문에 `ls -al` 명령어를 타이핑하면 항상 이 두개의 문자가 먼저 출력됩니다.
```
$ ls -al
```
![image](https://user-images.githubusercontent.com/1149996/47605489-03b9b900-da42-11e8-828d-4cf2ea705057.png)


### cd
경로를 이동하는 명령어

### ~
### /
### cp
### mv
### mkdir
### 숨김폴더, 숨김파일 만들기
### rm, rmdir
### pwd
### df, du
### cat
### more, head, tail
### which, whereis
### touch
### echo
### reboot
### shutdown now
