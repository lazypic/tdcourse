# 이슈관리와 코드제안(Pull Request)

프로젝트를 진행하다 보면 코드를 어떻게 협업해야하는지 모르는 분들이 많이 있습니다.
오늘은 코드관리툴에서 Pull Request 과정을 배워보겠습니다.

## 절 차
Git을 이용해서 협업하는 절차는 다음과 같습니다.
이 절차는 github, gitlab, bitbucket, gogs, gittea 등 모드 git 버전관리툴에서 사용할 수 있습니다.

- Fork
- Upstream 등록
- 이슈작성
- 이슈선정
- 이슈로 브런치 생성
- 코드수정
- 코드제안
- 투표
- 코드합치기

## Fork
소프트웨어 엔지니어링에서 Fork란 한 소프트웨어에서 소스코드를 다른곳으로 카피하는것을 뜻합니다.
회사 내부에 사용되는 코드를 직접 수정하게되면 수많은 버그가 발생할 수 있습니다. 언제나 코드를 Fork 하고 개발하는것을 추천합니다.
Github에서는 리포지터리 페이지 상단 Fork 버튼을 이용해서 Fork 작업을 진행할 수 있습니다.

woong 사용자 이름으로 Fork 되었다면 해당 리포지터리의 코드를 수정하기 위해 터미널에서 clone 할 수 있습니다.
```bash
$ git clone https://github.com/woong/tdcourse
```

## Upstream
리포지터리는 보통 Upstream과 Downstream 으로 이우러져 있습니다.
Fork를 진행하면 복사된 소스코드의 원래 소스코드가 Upstream이 되는 것이지요. 자신의 소스코드는 Downstream이 됩니다.
여러 회사들은 이미 이 방식으로 개발을 진행하고 있습니다. 진짜인지 확인하기 위해 Pixar OpenTimelineIO 리포지터리에서 upstream 을 사용고 있는 페이지에 놀러가보겠습니다. 구경가보죠! https://opentimelineio.readthedocs.io/en/latest/tutorials/contributing.html

upstream 을 등록하는 방법은 아래와 같습니다.
```bash
$ git remote add upstream https://github.com/lazypic/tdcourse
```

## 이슈작성
개발을 하다보면 아무래도 이슈가 발생하기 마련입니다. 좋은 프로그램은 수많은 이슈를 처리해가면서 탄생하니까요.
최대한 다른 사람을 배려하는 글을 쓰는 습관을 들이는 것이 좋습니다. 필요에 따라서 이미지를 첨부하면 좋습니다.

CentOS7.6에서는 `Shift + PrintScreen` 키를 누르면 마우스로 드레그 영역을 지정하여 이미지 캡쳐를 할 수 있습니다.
macOS에서는 `Command + Shift + 4` 키를 누르면 마우스로 드레그 영역을 지정하여 이미지 캡쳐를 할 수 있습니다.
또한 태그를 달아두면 이슈를 관리하기 쉽습니다. 또한 누가 이 일을 처리할지 등록도 해둘 수 있습니다.

이슈가 많이 활성화 된 리포지토리 하나를 방문해보겠습니다. 어떤 이야기가 오고 가는지, 태그는 무엇을 사용하는지 관찰해보세요.

https://github.com/wesnoth/wesnoth/issues

## 이슈선정
협업을 하는 모든 개발자마다 역량과 경험이 다릅니다. 자신이 처리할 수 있는 이슈 하나를 선정하고 그 이슈가 끝날때까지 프로그래밍을 진행합니다.
중요한것은 한 이슈가 끝날때까지 다른 이슈를 처리하지 않거나 진행하더라도 진행중인 이슈와 크게 관련없는 이슈를 다른 개발자와 병행진행해야 한다는 것 입니다.
비슷한 이슈를 처리하면 나중에 코드를 합칠 때 Conflict 가 발생할 확률이 높기 때문입니다.

## 이슈로 브런치 생성
이슈를 생성하면 이슈번호가 자동 생성됩니다. 이 번호를 이용해서 브런치를 생성하는 것이 좋습니다.
만약, 이슈번호가 113번 이라면 저는 iss113 으로 브런치를 생성하는 편입니다.

```bash
$ git branch iss113
```

## 코드수정
코드를 수정할 때는 master 브런치를 사용하지 않습니다. master 브런치는 upstream과 donwstream의 통로로만 사용하는 것을 추천합니다.

코드 수정을 위해서 iss113 브런치로 체크아웃 후 코드를 수정합니다.

```bash
$ git checkout iss113
```

## 코드제안(Pull Request - PR)
코드를 수정했다면 iss113 브런치로 Pull Request 작업을 진행합니다.
메인테이너(리포지터리관리자)와 코드의 구조나, 이름, 최적화 등등으로 토론하게 되죠.

미리 코드를 짜기전에 이슈, 토론으로 해당 코드를 짠다고 이야기 후 진행하세요. 이미 코드를 다 작성하고 여러분의 코드가 받아들여지지 않으면 허무하니까요. 이 점은 회사에 입사하더라도 비슷한 상황이 발생합니다.

Pull Request가 활발하게 일어나는 리포지터리 예제 링크.
코드가 충돌나거나 받아들여지지 않는 과정을 관찰해보세요.

https://github.com/wesnoth/wesnoth/pulls

## 투표
투표 방식은 간단합니다. 일반적으로 아래 패턴을 사용하게 됩니다.
- `+2`: 당신의 코드에 동의합니다.
- `+1`: 잘 모르겠지만 방향성에 대해서 동의합니다.
- `-2`: 당신의 코드에 동의하지 않습니다.

질문 또는 왜 코드를 이러한 방식으로 짰는지 설명을 하거나 질의를 진행합니다.

## 코드합치기
모든 상황에 해서 서로가 만족한다면, Merge 버튼을 눌러서 코드를 합치게 됩니다. 의견에 대해서 분쟁이 있다면 최종 결정은 해당 리포지터리의 메인테이너가 합니다.

## 실습진행
