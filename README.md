# Curriculum

## 기본정보 ![Progress](http://progressed.io/bar/46?title=progress)
- 교육내용 : Technical Director 기초과정 / 리눅스를 활용한 VFX, 애니메이션 파이프라인
- 교육방식 : Github를 활용한 교육 및 협업개발
- 문 의 : 김한웅 / hello@lazypic.org
- 프로그래밍이 처음이라면 한번씩 읽고 오세요 : https://wikidocs.net/book/2

## 내 용
1. [x] 소개 (12.28)
	1. PPT 발표, 개요
	1. [Technical Director Course 소개](docs/intro.md)
	1. [개발자가 보는 시장 : VFX, 애니메이션, 게임](docs/market.md)
	1. [회사의 발전단계](docs/techtree.md)
	1. [왜 리눅스를 사용하는가?](docs/why_linux.md)
	1. [강의를 위한 단축키](docs/ppt_hotkey.md)
	1. [Github와 오픈소스 이야기](docs/github.md)
	1. [Github 그룹 설정](docs/github_org_setting.md)
	1. [포트폴리오 마케팅용 github.io 소개](docs/github_io.md)
	1. [linkedin](docs/linkedin.md)

1. [x] 리눅스 설치1 (12.31)
	1. USB, SSD 전달
	1. [Linux설치 - CentOS 7.6](docs/install_centos.md)
	1. 실습 : 같이 CentOS 둘러보기

1. [x] 리눅스 설치2(1.2)
	1. [그래픽카드 드라이버 설치](docs/install_nvidia.md)
	1. [Grub셋팅](docs/setup_grub.md)
	1. [규칙](docs/rule.md)
	1. 실습 : 같이 CentOS 둘러보기

1. [x] 리눅스 명령어 기본(1.3)
	1. [리눅스의 기본 명령어](docs/linux_cmd.md)
	1. [리다이렉트, 파이프](docs/redirect_pipe.md)
	1. [리네임](docs/rename.md)
	1. [권한 이해하기](docs/permission.md)

1. [x] 리눅스 명령어 심화(1.4)
	1. [yum](docs/yum.md) 명령어
	1. [재미있는 명령어 설치](docs/fun_cmds.md)
	1. [쉘 이야기](docs/shell.md)
	1. [홈디렉토리 영문설정](docs/centos_home_kr2en.md)
	1. [시간설정, 타임서버](docs/time.md)
	1. [리눅스 네트워크 명령](docs/linux_net_cmd.md)
	1. [커널부터 응용프로그램까지](docs/linux_struct.md)

1. [x] 뉴크설치(1.7)
	1. [뉴크 설치](docs/install_nuke.md)
	1. [뉴크 버전관리](docs/managing_nukever.md)
	1. [뉴크 라이센스 셋팅](docs/license.md)
	1. 뉴크 실행하고 둘러보기
	1. 프로세스, Grep
		1. [프로세스 이해](docs/process.md)
		1. [top](docs/top.md)
		1. [find, grep, ripgrep](docs/find_grep.md)
	1. [스터디 그룹을 위한 컴파일러 설치](docs/gcc.md)
	
1. [x] 기타 유틸리티 설치(1.7)
	1. 실습 : 오피스 제품을 설치하고 MPAA 문서보기
	1. [크롬설치](docs/install_chrome.md)
	1. [CentOS Beep 사운드 제거](docs/soundoff.md)
	1. [Torrent](docs/torrent.md)
	1. [Steam](docs/steam.md)
	1. [MPV 플레이어 설치](docs/mpv.md)

1. [x] 데몬(서비스)(1.8)
	1. [Daemon](docs/daemon.md)
	1. [VNC](docs/vnc.md)
	1. [sFTP](docs/sftp.md)

1. [x] 에디터(1.9)
	1. [Vim 기본 사용법](docs/vim.md)
	1. [에디터 설치](docs/editor.md)
	1. 토론 : [에디터 선정](docs/talk_about_editor.md) / Vim으로 결정

1. [x] 유용한 시스템 명령어 / 폴더구조 (1.9)
	1. [crontab](docs/crontab.md)
	1. [notify](docs/notify.md)
	1. [man](docs/man.md)
	1. [Linux 폴더구조](docs/foldertree.md)

1. [x] [버전관리의 중요성](docs/version_control_system.md) (1.10)
	1. [Git 설치 / 설정](docs/init_git.md)
	1. [Git 명령어의 기초](docs/git_basic.md)
	1. 모두 같은 에디터를 사용하고 설정을 공유하는 리포지터리 제작
	1. Readme 문서 작성을 위한 [Markdown 문법배우기](docs/markdown.md)

1. [x] 쉘 스크립트 (1.11)
	1. [.sh 스크립트 생성](docs/shell_script.md)
	1. 실습 : [trans 명령 자동설치 스크립트](docs/install_trans.md)

1. [x] [환경변수란?](docs/env.md) (1.14)
	1. [자신만의 .bashrc 셋팅하기](docs/custom_bashrc.md)
	1. [환경변수 및 패키징 관리툴](docs/env_managing.md)

1. [x] 예제파일 설치하기 (1.15)
	1. ~/examples 설치 : `cd ~ && git clone https://github.com/cgiseminar/examples`
	1. [샘플파일설치](docs/sample.md)

1. [x] 동영상과 코덱 (1.16)
	1. [Player](docs/player.md)
	1. [동영상 포멧과 Codec](docs/format_codec.md)

1. [x] Github로 협업하기 (1.17)
	1. [Git 협업방식 설명](docs/github_collaboration.md)
	1. [이슈, Pull Request 상태에서의 토론](docs/discussion.md)
	1. [gitk](docs/gitk.md)
	1. 실습 : Git 협업모델 테스트

1. [x] [파이썬 X in Y minutes 1부](docs/python_x_in_y_min.md) (1.18)

1. [x] [파이썬 X in Y minutes 2부](docs/python_x_in_y_min.md) (1.21)
	- 함수 예제 작성

1. [x] [파이썬 X in Y minutes 3부](docs/python_x_in_y_min.md) (1.22)
	- 클래스 예제 작성, github.io 개발시작

1. [x] 파이썬 기초 실무 (1.23)
	1. [파이썬 함수 만들기](docs/python_make_function.md)
	1. [파이썬 클래스 만들기](docs/python_make_class.md)

1. [x] [경로기반의 파이프라인](docs/path_based_pipeline.md) (1.24)
	1. addproject 명령어 제작하기
	1. [Python : 경로를 분리하는 방법](docs/path_control.md)

1. [x] [Python : 레귤러 익스프레션](docs/path_regexp.md) (1.25)
	1. pathapi.py 제작하기 1부

1. [x] 개발자 유틸리티 설치(1.28)
	1. [pip](docs/pip.md) 설치
	1. [cmake](docs/cmake.md) 설치
	1. pathapi.py 제작하기 2부

1. [x] 프로그램을 만들기전에 알아야 할 기본적인 지식(1.29)
	1. [명령어의 구성요소 - 인수편](docs/command.md)
	1. [Python argv 처리](docs/python_argv.md)
	1. [우리가 프로그래밍으로 하는 대부분의 일](docs/add_set_rm_get.md)
	1. [파이프라인의 기본 Input, Output](docs/input_output.md)
	1. [Standard Streams](docs/standard_streams.md)
	1. [Python Test코드 작성하기](docs/python_testcode.md)
	1. [바이너리와 아스키](docs/binary_ascii.md)
	1. [의존성이야기](docs/dependency.md)
	1. [의존성을 최소화 하기 위해서 사용했던 Go 언어](docs/ldd.md)

1. [x] 파일변환 유틸리티 : ImageMagick (1.30)
	1. [촬영데이터 복사](docs/copy_onsetdata.md)
	1. [파일 변환 유틸리티](docs/convert_util.md)
	1. [ImageMagick](docs/imagemagick.md)
	1. [실습 : ImageMagick + python subprocess 활용](docs/python_imagemagick.md)

1. [x] 파일변환 유틸리티 : FFmpeg 1부 (1.31)
	1. [FFmpeg](docs/ffmpeg.md)
	1. 실습 : FFmpeg를 이용해서 일괄 동영상 변환 스크립트 제작

1. [x] 파일변환 유틸리티 : FFmpeg 2부 (2.1)
	1. 실습 : FFmpeg를 이용해서 일괄 동영상 변환 스크립트 제작
	1. [ffmpeg 명령어를 이용해서 개발내용 스크린 캡쳐](docs/ffmpeg_screencap.md)

1. 파일변환 유틸리티 : Mencoder, HandBrake, Mediainfo
	1. 뉴크 라이센스 갱신
	1. [mediainfo](docs/mediainfo.md)
	1. [mencoder](docs/mencoder.md)
	1. [HandBrake](docs/handbrake.md)

1. 파일변환 유틸리티 : OpenImageIO
	1. [컬러스페이스의 역사](docs/history_colorspace.md)
	1. [OpenImageIO 설치](docs/openimageio.md)

1. [VFX Platform 소개](docs/vfx_platform.md)
	1. [NumPy](docs/numpy.md)

1. [파이썬을 이용해서 엑셀파일 읽기, 쓰기](docs/excel_python.md)

1. VFX에서 자주 사용되는 파일 : 촬영, 현장데이터
	1. [촬영데이터 파일명의 구조](docs/raw_name.md)
	1. [raw2exr](docs/arriconverter_cmd.md)
	1. [metaextractor](docs/arri_metaextract.md)
	1. [현장데이터 수집툴](docs/setellite.md)
	1. [기타 현장데이터 종류](docs/etc_onsetdata.md)

1. VFX에서 자주 사용되는 파일 : 컬러매니징(DI), 편집작업
	1. [ACES / OpenColorIO](docs/opencolorio.md)
	1. [Lut](docs/lut.md)
	1. [OpenColorIO Lut](docs/opencolorio_lut.md)
	1. [EDL](docs/edl.md)
	1. [OpenTimelineIO](docs/opentimelineio.md)

1. [프로젝트 매니징 파이프라인툴](docs/pipeline_tools.md)

1. VFX에서 자주 사용되는 파일 : OpenEXR
	1. [OpenEXR](docs/openexr.md)
	1. [OpenEXR 명령어](docs/openexr_cmd.md)

1. [VFX에서 자주 사용되는 설정파일](docs/etc_files.md)

1. VFX에서 자주 사용되는 파일 : 3D 데이터
	1. 마야데이터 : .mb .ma
	1. 맥스 : .max
	1. .fbx
	1. [Obj](docs/obj.md)
	1. [Alembic](docs/abc.md)
	1. [USD](docs/usd.md)

1. VFX에서 자주 사용되는 파일 : 쉐이더
	1. [OpenShandingLanguage](docs/osl.md)

1. VFX에서 자주 사용되는 파일 : 볼륨데이터
	1. [OpenVDB](docs/openvdb.md)

1. GUI제작-1
	1. [GUI 솔루션](docs/gui_solution.md)
	1. [간단한 GUI : zenity](docs/zenity.md)
	1. [Zenity 응용 : 사용자 환경변수 등록](docs/setuser.md)
	1. [Pyside2 알아보기](docs/pyside2_gui.md)

1. GUI제작-2
	1. [Qt Designer 설치](docs/qt_designer.md)
	1. [.ui 파일과 python의 연동](docs/load_ui_from_python.md)
	1. 간단한 Pyside2 프로그램 제작

1. TheFoundry Nuke를 알아보는 시간.
	1. [개발에 도움이 되는 사이트](docs/help_nukedev.md)
	1. [뉴크에서 파이썬창을 띄우는 방법](docs/python_in_nuke.md)
	1. [뉴크 내부에서 사용하는 파이썬 버전을 확인하기](docs/check_py_ver_in_nuke.md)

1. 뉴크에서 활용 가능한 다양한 개발 방법론 소개
	1. [OFX(OpenFX)](docs/openfx.md)
	1. [Blink](docs/blink.md)
	1. [NDK](docs/ndk.md)
	1. PythonAPI : 앞으로 우리가 가장 많이 다루게 될 주제입니다.

1. Nuke 셋팅을 위한 Repository 생성
	1. [핫코너 옵션 끄기](docs/off_hotcorner.md)
	1. [NUKE_PATH 연결](docs/nuke_path.md)(★☆☆☆☆)
	1. [init.py, menu.py 생성](docs/set_init_menu_py.md)(★☆☆☆☆)
	1. [뉴크셋팅 폴더 구조생성](docs/set_assets_dir.md)(★☆☆☆☆)

1. 기즈모 제작
	1. [뉴크 익스프레션](docs/nuke_exp.md)
	1. [뉴크 Text 노드에서 자주 사용되는 익스프레션](docs/nuke_text_exp.md)
	1. [TCL](docs/tcl.md)
	1. [Nuke Gizmo : Timecode 뷰어](docs/gen_timecode_gizmo.md)(★☆☆☆☆)
	1. [Nuke Gizmo : Slate제작](docs/gen_slate_gizmo.md)(★★☆☆☆)
	1. [Nuke Gizmo등록](docs/add_gizmo.md)(★☆☆☆☆)

1. [Nuke Pedia 사이트 소개](docs/nukepedia.md)

1. Nuke Command Line Rendering
	1. [Nuke Command Line Rendering](docs/nuke_cmd.md)
	1. [Render Management Tools 소개](docs/render_management_tools.md)

1. 메뉴, ViewLut 설정
	1. [뉴크 메뉴바 생성](docs/create_menu.md)(★☆☆☆☆)
	1. [Arri Alexa lut 다운로드](docs/download_arri_lut.md)(★☆☆☆☆)
	1. [Viewport LUT 설정](docs/set_viewlut_in_nuke.md)(★★☆☆☆)

1. 간단한 뉴크 스크립트
	1. [자주 사용하는 포멧등록](docs/add_format.md)(★☆☆☆☆)
	1. [노드구조 퍼포먼스 체크 기능 추가하기](docs/performance_time_check.md)(★☆☆☆☆)
	1. [환경변수 체크 스크립트 제작](docs/nuke_getenv.md)(★☆☆☆☆)
	1. [노드에 file 옵션이 있다면 폴더를 여는 기능 제작](docs/nkpython_openfile.md)(★★☆☆☆)
	1. 실습 : 작업시 활용되는 in 소스 폴더 열기 기능 제작(★★☆☆☆)

1. Nuke GUI
	1. [예제 : 뉴크 PySide2를 이용해서 GUI 제작](docs/nuke_pyside2.md)(★☆☆☆☆)
	1. [Write노드 생성 스크립트 제작](docs/gen_writenode.md)(★★★☆☆)

1. 라이브러리의 기초
	1. [경로를 통해서 Read노드 만들기](docs/path_to_read.md)(★★☆☆☆)
	1. [다른 .nk 노드를 내부로 불러오기](docs/load_nk.md)(★★★☆☆)

1. 자주 사용하는 플러그인 설치해보기
	1. [크립토매트 설치해보기](docs/cryptomatte.md)(★★☆☆☆)
	1. [루마픽쳐스에서 사용중인 기즈모 등록](docs/lumapic.md)(★★★☆☆)
	1. [다른 작업에 사용되는 플러그인 셋팅](docs/set_other_plugins.md)

1. [파일관리툴 제작](docs/make_opener.md)(★★★★☆)
	
1. DB 소개 및 활용예
	1. [DB의 종류](docs/db.md)
	1. [Redis 설치](docs/install_redis.md)
	1. [Redis PythonAPI 실습](docs/python_redis.md)
	1. [MongoDB 설치](docs/install_mongodb.md)
	1. [MongoDB PythonAPI 실습](docs/pymongo.md)
	1. [PostrgreSQL 설치](docs/install_postrgresql.md)
	1. [PostrgreSQL PythonAPI 실습](docs/python_postrgresql.md)
	
1. [응용 및 실습](docs/dev_todo.md)

1. 포트폴리오 진행
	1. 남은 8시간은 하루동안 기존에 배운것들을 천천히 정리하는 시간입니다.
	1. 기술지원, 멘토링 지원
	1. github를 이용한 포트폴리오 제작. README.md 작성
	1. 기술공유, 추후 정보를 나눌 채널, 이슈정리, 커뮤니케이션 약속 정하기
	1. SSD제거 및 반납, 수료증 전달, 카페토론
