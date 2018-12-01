# OpenEXR 명령어
OpenEXR을 컴파일하면 bin 폴더에 아래 명령어들이 생성됩니다.
이 명령어들을 이용하면 필요시 파이프라인을 개선할 수 있습니다.

## exrenvmap
makes openexr environment maps

## exrmakepreview
for creating preview images for OpenEXR files.

## exrmultipart
exrmultipart -separate -i infile.exr -o outfileBaseName [option]
exrmultipart -convert -i infile.exr -o outfile.exr [option]

## exrstdattr
a utility for modifying openexr standard attributes.
http://manpages.ubuntu.com/manpages/xenial/man1/exrstdattr.1.html

## exrheader
utility to print an openexr image files header
$ exrheader imagefile

## exrmaketiled
For generating tiled and rip/mipmapped images.
mipmap, ripmap 설명하기.

## exrmultiview
exrmultivew left imgL.exr right imgR.exr imgLR.exr

	이렇게 하면 다시 아래처럼 응용 가능
	exrmultipart -convert -i imgLR.exr -o imgLR_multipart.exr
	https://openexr-devel.nongnu.narkive.com/q1Cos7DF/multipart-backward-compatibility