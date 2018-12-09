# Process

## ps
컴퓨터에서 실행되고 있는 프로세스를 출력합니다.
아티스트는 다운된 소프트웨어를 강제로 끄기 위해서 자주 사용합니다.

```
$ ps
$ ps -ef
$ ps -ef | grep Nuke
```

## kill
```
$ kill {pid}
$ pkill Nuke # Nuke가 들어가는 모든 프로세스를 종료합니다.
```

## pstree
프로세스 구조를 트리구조로 출력합니다.

```
$ pstree
```
