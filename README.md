# curriculum

#### Info
- 장 소 : [mofacacademy](https://www.mofacacademy.com)
- 인 원 : 25명 모집
- 기 간 : 18.12.28 ~ 19.2.27 
- 시 간 :월~금
	- 2019년 1월 : 오전 10시~오후3시 4시간 / 2시간 교육, 2시간 실습
	- 2019년 2월 : 오전 10시~오후7시 8시간 / 4시간 교육, 4시간 실습
	- 점심시간 : 오후 1시
- 교육내용 : Technical Director 기초과정
- 교육방식 : Github를 활용한 협업방식, 리눅스를 활용한 VFX, 애니메이션 파이프라인
- 라이센스 지원 : The foundry Nuke
- 강의자리 : 총 21석
- 문 의 : hello@lazypic.org

구 분|강 의|실 습| 내 용
----|----|----|----
12월28일|2시간|2시간|강의소개, 리눅스 설치
1월2일~4일|2시간|2시간|리눅스
1월7일~11일|2시간|2시간|환경변수, Git
1월14일~18일|2시간|2시간|응용유틸리티, PythonScript
1월21일~25일|2시간|2시간|VFX포멧, Nuke 익스프레션,기즈모
1월28일~2월1일|2시간|2시간|NukeAPI
2월7일~2월8일|4시간|4시간|설날, NukeAPI, 포트폴리오 기획단계
2월11일~2월15일|4시간|4시간|NukeAPI
2월18일~2월22일|4시간|4시간|NukeAPI / 포트폴리오 준비
2월25일~2월27일|4시간|4시간|포트폴리오 정리

#### 내 용
1. 강의 소개, 리눅스 설치
	1. [Technical Director Course 소개](intro.md)
	1. 개발자의 시선으로 바라보는 시장 흐름 : VFX, 애니메이션, 게임
	1. [기업은 왜 리눅스를 사용하는가?](why_linux.md)
	1. [Linux설치 - CentOS 7.5](install_centos.md)
	1. 실습 : Linux 설치를 위한 USB 만들기
	1. 실습 : CentOS 둘러보기
1. 리눅스 설치, 리눅스 명령어 기본
	1. [리눅스의 기본 명령어](linux_cmd.md)
	1. [리다이렉트, 파이프](redirect_pipe.md)
	1. [리네임](rename.md)
1. 리눅스 명령어 심화
	1. [권한 이해하기](permission.md)
	1. [쉘 이야기](shell.md)
	1. [커널부터 응용프로그램까지](linux_struct.md)
	1. [프로세스 이해](process.md)
	1. [find, grep, ripgrep](find_grep.md)
	1. [시간설정, 타임서버](time.md)
	1. [리눅스 네트워크 명령](linux_net_cmd.md)
1. 에디터, 유틸리티 설치
	1. [vim 소개](vim.md)
	1. [에디터 추천](editor.md)
	1. 실습 : Vim관련 자료, 다른 기능들을 탐구해보자.
	1. 실습 : Thunderbird 설치
	1. 실습 : LibreOffice 설치
	1. 실습 : 크롬설치 https://blog.bypass.sh/961
	1. [CentOS Beep 사운드 제거](soundoff.md)
1. 설치 유틸리티
	1. [yum](yum.md)
	1. 실습 : 재미있는 명령어를 설치해보자. https://www.binarytides.com/linux-fun-commands/
	1. make
	1. NumPy 설치
	1. [pip](pip.md) 설치

1. 유용한 시스템 명령어
	1. [crontab](crontab.md)
	1. [notify](notify.md)
	1. [top](top.md)
	1. [man](man.md) : https://unix.stackexchange.com/questions/3586/what-do-the-numbers-in-a-man-page-mean
1. 서비스와 데몬
	1. [Daemon](daemon.md)
	1. [vnc](vnc.md)
	1. [ftp, sftp](ftp.md)
1. [Linux 폴더구조](foldertree.md)

1. 뉴크 설치
	1. 실습 : 뉴크 설치 / 라이센스 셋팅
1. 쉘 스크립트
	1. .sh 스크립트 생성
	1. 실습 : trans 명령을 자동으로 설치하는 .sh 파일을 만들어보기
1. [환경변수란?](env.md)
	1. 환경변수 관리 툴
		1. 패키징 관리툴 : [Rez](https://github.com/nerdvegas/rez/wiki)
		1. [Ecosystem](https://github.com/PeregrineLabs/Ecosystem)
		1. [run](https://github.com/studio2l/run)
	1. 실습 : [자신만의 .bashrc 셋팅하기](custom_bashrc.md)
1. 팀규모의 에디터 셋팅
	1. 토론 : 이 강의실의 모든 사람이 같이 사용할 에디터를 리서치하기. 왜 그 에디터를 사용해야하는지 이유도 설명하기.
	1. 토론 : 모두가 사용할 에디터 선정회의
1. [버전관리의 중요성](version_control_system.md)
	1. [Git 설치 / 설정](init_git.md)
	1. [Git 명령어의 기초](git_basic.md)
	1. 실습 : [Pro Git](https://git-scm.com/book/ko/v2)
	1. [Github와 오픈소스 이야기](github.md)
	1. 토론 : Github 가입, 학생들의 Github ID 제출
	1. 모두 같은 에디터를 사용하고 설정을 공유하는 리포지터리 제작
1. Git, Readme 작성을 위한 [Markdown 문법배우기](https://guides.github.com/features/mastering-markdown/)
	1. [Git 협업방식 설명](github_collaboration.md)
	1. 실습 : Git 협업모델 테스트
	1. [이슈, Pull Request 상태에서의 토론](discussion.md)

1. 동영상과 코텍
	1. [Player](player.md)
	1. [동영상 포멧과 Codec](format_codec.md)
1. 파일변환 유틸리티
	1. [파일 변환 유틸리티](convert_util.md)
		1. [ImageMagick](imagemagick.md)
		1. 실습 : ImageMagick + python을 이용한 이미지 일괄 변환 스크립트 제작
		1. [FFmpeg 소개](ffmpeg.md)
		1. 실습 : FFmpeg를 통한 동영상 변환
		1. 실습 : FFmpeg를 이용해서 일괄 동영상 변환 스크립트 제작
		1. [HandBrake](handbrake.md)
		1. 실습 : HandBrakeCLI를 이용해서 일괄 Proxy 동영상 생성
		1. [mediainfo 설치](mediainfo.md)
		1. 실습 : mediainfo 활용하기
		1. [컬러스페이스의 역사](history_colorspace.md)
		1. [OpenImageIO 설치](openimageio.md)
1. [경로기반의 파이프라인](path_based_pipeline.md)
	1. Python : 경로를 분리하는 방법
	1. Python : 레귤러 익스프레션
1. OpenEXR
	1. [OpenEXR 컴파일](openexr.md)
	1. OpenEXR 명령어
		1. exrenvmap
		1. exrmakepreview
		1. exrmultipart
		1. exrstdattr
		1. exrheader
		1. exrmaketiled
		1. exrmultiview
1. 프로그램을 만들기전에 알아야 할 기본적인 지식
	1. [명령어의 구성요소](command.md)
	1. [우리가 프로그래밍으로 하는 대부분의 일](add_set_rm_get.md)
	1. [파이프라인의 기본 Input, Output](input_output.md)
	1. [Standard Streams](standard_streams.md)
	1. [Python Test코드 작성하기](python_testcode.md)
	1. 바이너리와 아스키

1. [의존성이야기](dependency.md)
	1. 의존성을 설명하기전에 ldd 명령어 사용법

1. VFX에서 자주 사용되는 파일
	1. 촬영데이터 파일명의 구조
	1. OpenEXR
	1. ACES / OpenColorIO
	1. Lut : .3dl, .blut, .cms, .csp, .csp, .cub, .cube, .vf, .vfz
	1. OpenColorIO Lut : .cc, .ccc
	1. EDL
	1. json, xml, ini(예, Unreal설정파일)
	1. OSL
	1. OpenVDB
	1. Alembic
	1. USD

1. 파이프라인툴 이야기 : Shotgun, Ftrack, Tactic, 인하우스툴
1. [VFX Platform 소개](https://www.vfxplatform.com)
	1. [gcc설치](install_gcc.md)
	1. [pip 설치](pip.md)
	1. [Pyside2 설치](pyside2.md)
	1. Qt Designer 설치
	

1. GUI제작-1
	1. [간단한 GUI : zenity](zenity.md)
	1. python을 이용한 기초 GUI 제작

1. GUI제작2
	1. Qt Designer로 GUI 제작하기
	1. .ui 파일과 python의 연동

1. 파이썬을 이용해서 엑셀파일 읽기, 쓰기

1. DB의 종류. 사용되는 예
	1. MySQL 설치
	1. MySQL PythonAPI 실습
	1. PostrgreSQL 설치
	1. PostrgreSQL PythonAPI 실습
	1. MongoDB 설치
	1. MongoDB PythonAPI 실습
	1. Redis 설치
	1. Redis PythonAPI 실습

1. VFX와 관련된 라이브러리
	1. ptex 컴파일 : https://github.com/wdas/ptex
	1. intel TBB : http://m.cafe.daum.net/betterspeed/8V7A/3?q=D_jDGwPlH16FY0&
	1. intel Math Kernel Library : https://software.intel.com/en-us/mkl
	1. OpenVDB 컴파일
	1. OpenSubdiv
	1. Alembic
	1. [USD](usd.md)

1. 뉴크를 개발하기전에 알아야할 기본지식
	1. https://community.foundry.com/discuss/forum/191/nuke-dev
	1. https://www.foundry.com/products/nuke/developers
	1. 뉴크에서 파이썬을 실행하는 방법
	1. 뉴크 내부에서 사용하는 파이썬 버전을 확인하기
	1. 뉴크 버전관리

1. Nuke 셋팅을 위한 Repository 생성
	1. 폴더 구조생성 : lib, python, gizmo, images, lut
	1. NUKE_PATH 연결
	1. .nuke설정
	1. init.py, menu.py 설정

1. Nukepedia 사이트 소개 : http://www.nukepedia.com/
	1. 실습 : nukepedia 가입 및 살펴보기
	1. 플러그인 설치해보기

1. 기즈모 제작
	1. 뉴크 익스프레션
	1. 뉴크 Text 노드에서 자주 사용되는 익스프레션
	1. [TCL](https://www.tcl.tk/)
	1. Gizmo knob 생성
	1. Nuke Gizmo : Slate제작
	1. Nuke Gizmo : Timecode 뷰어

1. Nuke Command line
	1. 실습 : Nuke Command line Rendering & Python
	1. Render management Tools 소개
		1. Tractor : https://renderman.pixar.com/tractor
		1. Deadline : https://deadline.thinkboxsoftware.com/
1. 메뉴, 뷰어 설정
	1. 뉴크 메뉴생성
	1. 뉴크 단축키 설정
	1. 아이콘 넣기
	1. LUT 설정
		1. Alexa lut 다운로드
		1. Viewport에 lut 넣기
1. 인아웃 셋팅
	1. Read 노드에서 정보 가지고 오기
	1. Write노드 생성 스크립트 제작
	1. .nk 파일에서 아스키 정보를 이용해서 소스 가지고 오기.
1. 유명한 플러그인 설치해보기
	1. 크립토매트 설치해보기
	1. 타팀에서 사용하는 플러그인 셋팅. 예)3DE
1. 노드로 폴더를 여는 스크립트 제작
1. Python으로 노드짜기
	1. 예제 : Pyside2를 이용해서 스크립트 실습
	1. 다른 개발방법들 : blink, NDK, OpenFX
1. 포트폴리오 준비 1
	1. 개인 포트폴리오 홈페이지 제작을 위한 github.io 소개
	1. ffmpeg 명령어를 이용해서 개발내용 스크린 캡쳐하기
	1. 실습 : github.io를 통한 자신의 포트폴리오 사이트 제작
	1. 실습 : linkedin 작성
1. 포트폴리오 준비 2
	1. 실습 : 자신이 제작하고 싶은 프로그램 제작, 기술지원, 멘토링
	1. 포트폴리오 제작, 기술지원
	1. 발표, 기술공유
