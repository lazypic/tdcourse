# Samba

## macOS 에서 Samba 연결하기.
mount
```
$ mount_smbfs //user@SERVER/folder ./mntpoint
```

만약 워크그룹을 같이 설정한다면 다음처럼 설정합니다.

```
$ mount_smbfs -W workgroup //user@SERVER/folder ./mntpoint
```

unmount

```
$ umount ./mntpoint
```

## Reference
https://apple.stackexchange.com/questions/697/how-can-i-mount-an-smb-share-from-the-command-line
