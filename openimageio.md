# OpenImageIO

OpenImageIO는 VFX, 게임, 애니메이션 작업등 제작 파이프라인엣 사용할 수 있는 이미지 컨버팅 도구, API 입니다.
ACES(OpenColorIO)를 지원합니다.

이미지를 컨버팅함에 있어서 그 어떤 소프트웨어의 라이센스도 사용하지 않기 때문에 오픈소스로 파이프라인을 구축할 때 굉장히 파워풀한 도구가 됩니다.

### 지원하는 포멧
TIFF, JPEG/JFIF, OpenEXR, PNG, HDR/RGBE, ICO, BMP, Targa, JPEG-2000,
RMan Zfile, FITS, DDS, Softimage PIC, PNM, DPX, Cineon, IFF, Field3D,
OpenVDB, Ptex, Photoshop PSD, Wavefront RLA, SGI, WebP, GIF, DICOM,
많은 디지털카메라의 Raw포멧 등

### 설치
- CentOS7.5
```
# yum install OpenImageIO
# yum install OpenImageIO-utils
```

- macOS
```
$ brew install openimageio
```

- Windows
	- https://github.com/OpenImageIO/oiio/blob/master/INSTALL.md
	- https://sites.google.com/site/openimageio/building-oiio-on-windows

### .exr to .tga
일반적으로 exr 이미지는 linear 컬러스페이스를 가지며, tga는 sRGB 컬러스페이스를 가집니다.
oiiotool 디폴트로 알파에 대해서 premult를 하지 않으니 알파가 있는 exr 컨버팅시에는 꼭 `--premult` 옵션을 달아주세요.

```
$ oiiotool -i input.exr --colorconvert linear srgb --premult -o output.tga
```

### Reference
- https://github.com/OpenImageIO/oiio/blob/master/src/doc/openimageio.pdf
