# Edit metadata
> 참고 : 이 페이지는 강의 이후 작성된 페이지 입니다.

### openEXR

### Tiff
tif 파일은 exiftool 명령어를 이용해서 메타데이터를 수정할 수 있습니다.

#### 설치
```bash
$ brew install exiftool
```

메타데이터 키 확인
```
$ exiftool -v C02_v01_w01.0001.tif
```

Y Resolution 메타데이터 업데이트
```bash
$ exiftool -overwrite_original -YResolution=1 C02_v01_w01.0001.tif
```

- https://libre-software.net/edit-metadata-exiftool/