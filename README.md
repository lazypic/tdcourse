# curriculum

## Info
- 장 소 : [mofacacademy](https://www.mofacacademy.com)
- 기 간 : 18.12.28 ~ 19.2.27 
- 시 간 : 월 ~ 금
	- 2019년 1월 : 09:00 ~ 13:00 4시간 / 14:00 ~ 18:00 4시간 툴교육(뉴크,마야)
	- 2019년 2월 : 09:00 ~18:00 8시간 
	- 점심시간 : 13:00 ~ 14:00 / 지하2층 구내식당 / 식비는 학생부담 / 식권은 오후3~4시 구매가능
- 교육내용 : Technical Director 기초과정
- 교육방식 : Github를 활용한 협업방식, 리눅스를 활용한 VFX, 애니메이션 파이프라인
- 강의실 : 모집인원에 따라서 강의실이 결정됨.
	- A클래스 : 15석
	- B클래스 : 20석
- 문 의 : 김한웅 / hello@lazypic.org
- 강의실 시스템 엔지니어 : 김태진 차장 / 010-7794-3111
- 업무협의 : 정선화 부원장 / 010-8663-4626
- 준비물 : USB 1개 16기가 이상으로 준비할 것 (CentOS 7.5 이미지 설치용)
- 프로그래밍 기초가 약한 분들은 한번씩 읽고 오세요. : https://wikidocs.net/book/2

## 내 용
1. 강의 소개, 리눅스 설치
	1. [Technical Director Course 소개](docs/intro.md)
	1. [개발자의 시선으로 바라보는 시장 흐름 : VFX, 애니메이션, 게임](docs/market.md)
	1. [회사의 발전단계](docs/techtree.md)
	1. [기업은 왜 리눅스를 사용하는가?](docs/why_linux.md)
	1. [Linux설치 - CentOS 7.5](docs/install_centos.md)
	1. 실습 : 설치이후 CentOS 둘러보기
	1. [규칙](docs/rule.md)

1. 리눅스 설치, 리눅스 명령어 기본
	1. [리눅스의 기본 명령어](docs/linux_cmd.md)
	1. [리다이렉트, 파이프](docs/redirect_pipe.md)
	1. [리네임](docs/rename.md)

1. 리눅스 명령어 심화
	1. [권한 이해하기](docs/permission.md)
	1. [쉘 이야기](docs/shell.md)
	1. [커널부터 응용프로그램까지](docs/linux_struct.md)
	1. [프로세스 이해](docs/process.md)
	1. [find, grep, ripgrep](docs/find_grep.md)
	1. [시간설정, 타임서버](docs/time.md)
	1. [리눅스 네트워크 명령](docs/linux_net_cmd.md)

1. 에디터, 유틸리티 설치
	1. [vim 소개](docs/vim.md)
	1. [에디터 추천](docs/editor.md)
	1. 실습 : 크롬설치 https://blog.bypass.sh/961
	1. [CentOS Beep 사운드 제거](docs/soundoff.md)

1. 설치 유틸리티
	1. [yum](docs/yum.md) 설치
	1. 실습 : 재미있는 명령어를 설치해보자. https://www.binarytides.com/linux-fun-commands/
	1. [pip](docs/pip.md) 설치
	1. [NumPy](docs/numpy.md) 설치

1. 유용한 시스템 명령어
	1. [crontab](docs/crontab.md)
	1. [notify](docs/notify.md)
	1. [top](docs/top.md)
	1. [man](docs/man.md)

1. 서비스와 데몬
	1. [Daemon](docs/daemon.md)
	1. [vnc](docs/vnc.md)
	1. [ftp, sftp](docs/ftp.md)

1. [Linux 폴더구조](docs/foldertree.md)

1. 뉴크 설치
	1. 실습 : [뉴크 설치](docs/install_nuke.md)
	1. [라이센스 셋팅](docs/license.md)

1. 쉘 스크립트
	1. .sh 스크립트 생성
	1. 실습 : [trans 명령을 자동으로 설치하는 .sh 파일을 만들어보기](docs/install_trans.md)

1. [환경변수란?](docs/env.md)
	1. 환경변수 관리 툴
		1. 패키징 관리툴 : [Rez](https://github.com/nerdvegas/rez/wiki)
		1. https://github.com/est77/rez-packages
		1. [Ecosystem](https://github.com/PeregrineLabs/Ecosystem)
		1. [run](https://github.com/studio2l/run)
	1. 실습 : [자신만의 .bashrc 셋팅하기](docs/custom_bashrc.md)

1. 팀규모의 에디터 셋팅
	1. [에디터](docs/editor.md)
	1. 토론 : [에디터 선정](docs/talk_about_editor.md)

1. [버전관리의 중요성](docs/version_control_system.md)
	1. [Git 설치 / 설정](docs/init_git.md)
	1. [Git 명령어의 기초](docs/git_basic.md)
	1. 실습 : [Pro Git](docs/https://git-scm.com/book/ko/v2)
	1. [Github와 오픈소스 이야기](docs/github.md)
	1. 토론 : Github 가입, 학생들의 Github ID 공유하기
	1. 모두 같은 에디터를 사용하고 설정을 공유하는 리포지터리 제작

1. Git, Readme 작성을 위한 [Markdown 문법배우기](docs/markdown.md)
	1. [Git 협업방식 설명](docs/github_collaboration.md)
	1. 실습 : Git 협업모델 테스트
	1. [이슈, Pull Request 상태에서의 토론](docs/discussion.md)

1. 동영상과 코텍
	1. [Player](docs/player.md)
	1. [동영상 포멧과 Codec](docs/format_codec.md)

1. 파이썬 기초 실무
	1. [파이썬 X in Y minutes](https://learnxinyminutes.com/docs/python/)
	1. [파이썬 함수 만들기](docs/python_make_function.md)
	1. [파이썬 클래스 만들기](docs/python_make_class.md)

1. [경로기반의 파이프라인](docs/path_based_pipeline.md)
	1. [Python : 경로를 분리하는 방법](docs/ath_control.md)
	1. [Python : 레귤러 익스프레션](docs/path_regexp.md)
	
1. 프로그램을 만들기전에 알아야 할 기본적인 지식
	1. [명령어의 구성요소](docs/command.md)
	1. [우리가 프로그래밍으로 하는 대부분의 일](docs/add_set_rm_get.md)
	1. [파이프라인의 기본 Input, Output](docs/input_output.md)
	1. [Standard Streams](docs/standard_streams.md)
	1. [Python argv 처리](docs/python_argv.md)
	1. [Python Test코드 작성하기](docs/python_testcode.md)
	1. [바이너리와 아스키](docs/binary_ascii.md)

1. 파일변환 유틸리티
	1. [파일 변환 유틸리티](docs/convert_util.md)
	1. [ImageMagick](docs/imagemagick.md)
	1. 실습 : ImageMagick + python을 이용한 이미지 일괄 변환 스크립트 제작
	1. [FFmpeg](docs/ffmpeg.md)
	1. 실습 : FFmpeg를 통한 동영상 변환
	1. 실습 : FFmpeg를 이용해서 일괄 동영상 변환 스크립트 제작
	1. [HandBrake](docs/handbrake.md)
	1. 실습 : HandBrakeCLI를 이용해서 일괄 Proxy 동영상 생성
	1. [mediainfo](docs/mediainfo.md)
	1. [컬러스페이스의 역사](docs/history_colorspace.md)
	1. [OpenImageIO 설치](docs/openimageio.md)

1. [의존성이야기](docs/dependency.md)
	1. [의존성을 확인할 수 있는 명령어 ldd](docs/ldd.md)

1. VFX에서 자주 사용되는 파일 : 촬영데이터
	1. [촬영데이터 파일명의 구조](docs/raw_name.md)

1. VFX에서 자주 사용되는 파일 : OpenEXR
	1. [OpenEXR](docs/openexr.md)
	1. [OpenEXR 컴파일](docs/openexr_compile.md)
	1. [OpenEXR 명령어](docs/openexr_cmd.md)

1. VFX에서 자주 사용되는 파일 : 컬러매니징
	1. [ACES / OpenColorIO](docs/opencolorio.md)
	1. [Lut](docs/lut.md)
	1. [OpenColorIO Lut](docs/opencolorio_lut.md)

1. VFX에서 자주 사용되는 파일 : 편집데이터
	1. [EDL](docs/edl.md)
	1. [OpenTimelineIO](docs/opentimelineio.md)

1. VFX에서 자주 사용되는 파일 : 쉐이더
	1. [OpenShandingLanguage](docs/osl.md)

1. [VFX에서 자주 사용되는 설정파일](docs/etc_files.md)

1. VFX에서 자주 사용되는 파일 : 3D 데이터
	1. [Obj](docs/obj.md)
	1. [Alembic](docs/abc.md)
	1. [USD](docs/usd.md)

1. VFX에서 자주 사용되는 파일 : 볼륨데이터
	1. [OpenVDB](docs/openvdb.md)

1. [파이프라인툴 이야기](docs/pipeline_tools.md)

1. [파이썬을 이용해서 엑셀파일 읽기, 쓰기](docs/excel_python.md)

1. [VFX Platform 소개](docs/vfx_platform.md)

1. GUI제작-1
	1. [GUI 솔루션](docs/gui_solution.md)
	1. [간단한 GUI : zenity](docs/zenity.md)
	1. [python Pyside2를 이용한 기초 GUI 제작](docs/pyside2_gui.md)

1. GUI제작-2
	1. [Qt Designer 설치](docs/qt_designer.md)
	1. [Qt Designer로 GUI 제작하기](docs/gen_qt_designer_gui.md)
	1. [.ui 파일과 python의 연동](docs/load_ui_from_python.md)

1. [DB의 종류](docs/db.md)
	1. [PostrgreSQL 설치](docs/install_postrgresql.md)
	1. [PostrgreSQL PythonAPI 실습](docs/python_postrgresql.md)
	1. [MongoDB 설치](docs/install_mongodb.md)
	1. [MongoDB PythonAPI 실습](docs/pymongo.md)
	1. [Redis 설치](docs/install_redis.md)
	1. [Redis PythonAPI 실습](docs/python_redis.md)

1. TheFoundry Nuke를 알아보는 시간.
	1. https://community.foundry.com/discuss/forum/191/nuke-dev
	1. https://www.foundry.com/products/nuke/developers
	1. [뉴크에서 파이썬창을 띄우는 방법](docs/python_in_nuke.md)
	1. [뉴크 내부에서 사용하는 파이썬 버전을 확인하기](docs/check_py_ver_in_nuke.md)
	1. [뉴크 버전관리](docs/managing_nukever.md)

1. Nuke 셋팅을 위한 Repository 생성
	1. [NUKE_PATH 연결](docs/nuke_path.md)
	1. [init.py, menu.py 생성](docs/set_init_menu_py.md)
	1. [폴더 구조생성](docs/set_assets_dir.md)

1. 기즈모 제작
	1. [뉴크 익스프레션](docs/nuke_exp.md)
	1. [뉴크 Text 노드에서 자주 사용되는 익스프레션](docs/nuke_text_exp.md)
	1. [TCL](docs/tcl.md)
	1. [Gizmo Knob 생성](docs/gen_knob.md)
	1. [Nuke Gizmo : Slate제작](docs/gen_slate_gizmo.md)
	1. [Nuke Gizmo : Timecode 뷰어](docs/gen_timecode_gizmo.md)

1. [Nukepedia 사이트 소개](docs/nukepedia.md)

1. Nuke Command line
	1. [Nuke Command line Rendering](docs/nuke_cmd.md)
	1. [Render Management Tools 소개](docs/render_management_tools.md)

1. 메뉴, 뷰어 설정
	1. [뉴크 메뉴생성](docs/create_menu.md)
	1. [뉴크 단축키 설정](docs/nuke_hotkey.md)
	1. [아이콘 넣기](docs/set_icon.md)
	1. LUT 설정
		1. [Arri Alexa lut 다운로드](docs/download_arri_lut.md)
		1. [Viewport LUT 설정](docs/set_viewlut_in_nuke.md)

1. 인아웃 셋팅
	1. [Read 노드에서 정보 가지고 오기](docs/get_readnode_info.md)
	1. [Write노드 생성 스크립트 제작](docs/gen_writenode.md)
	1. .nk 파일에서 소스정보를 가지고 오는 방법.

1. 자주 사용하는 플러그인 설치해보기
	1. [크립토매트 설치해보기](docs/cryptomatte.md)
	1. [타팀에서 사용하는 플러그인 셋팅](docs/set_other_plugins.md)

1. 노드로 폴더를 여는 스크립트 제작

1. Python으로 노드짜기
	1. 예제 : 뉴크 내부에서 PySide2를 이용해서 스크립트 제작

1. 뉴크에서 활용가능한 다른 개발방법들
	1. [OFX(OpenFX)](docs/openfx.md)
	1. [Blink](docs/blink.md)
	1. [NDK](docs/ndk.md)

1. 포트폴리오 준비
	1. [ffmpeg 명령어를 이용해서 개발내용 스크린 캡쳐](docs/ffmpeg_screencap.md)
	1. [개인 포트폴리오 홈페이지 제작을 위한 github.io 소개](docs/github_io.md)
	1. 실습 : github.io를 통한 자신의 포트폴리오 사이트 제작
	1. 실습 : [linkedin](https://www.linkedin.com) 가입 / 작성

1. 포트폴리오 진행
	1. 남은 8시간은 하루동안 기존에 배운것들을 천천히 정리하는 시간입니다.
	1. 기술지원, 멘토링
	1. github를 이용한 포트폴리오 제작. README 작성.
	1. 기술공유, 추후 정보를 나눌 채널, 이슈정리 약속 정하기