# 환경변수 관리
회사에는 수많은 부서, 팀, 개발자, 아티스트가 어우러저 컴퓨터를 사용하고 있습니다.
개발단계에서 필요한 환경변수가 현재 돌아가는 프로젝트에 영향을 주면 안되거나, 필요시 특수한 환경변수를 셋팅해서 사용해야하는 상황이 발생하기도 합니다. A프로젝트에 사용하는 환경변수가 B프로젝트에는 적용되면 안되기도 하죠.

보통 이런 과정을 잘 처리하기위해서 환경변수를 관리할 수 있는 툴을 사용합니다.
컴파일을 위한 패키징툴은 보통 이러한 환경변수를 잘 처리할 수 있도록 설계되어있어 환경변수를 관리하는데 사용하기도 합니다.

우리가 진행하는 강의는 우리가 제어할 수 있는 범위의 환경변수만 다루게됩니다.

~/env/init.env

아래 솔루션을 같이 살펴보고 특징만 소개하겠습니다.

## Res
- 위키 : https://github.com/nerdvegas/rez/wiki
- Res를 사용하는 개발자의 셋팅 예) : https://github.com/est77/rez-packages
- 4th회사는 공식적으로 Autodesk Univercity 2018 에서 Res를 사용한다고 발표했습니다.

## Ecosystem
- 소스코드 : https://github.com/PeregrineLabs/Ecosystem

## Studio2L
Studio 2L은 run이라고 하는 명령어를 직접 제작하여 사용합니다.
- 소스코드 : https://github.com/studio2l/run