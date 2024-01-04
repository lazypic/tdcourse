# Git branch

## Branch

Git branch 관리에 대해 설명합니다.

![gitbranch](../figures/gitbranch.png)

브랜치는 독립된 개발 라인을 만들 때 사용합니다. 새로운 기능이나 버그 수정작업을 할 때 브랜치를 사용하여 다른 팀 구성원의 작업과 자신의 작업을 분리할 때 사용합니다. Git 브랜치는 동일한 소스 코드에서 가져온 독립적인 개발 라인만들 때 사용할 수 있으며 브랜치끼리 병합할 수 있습니다.

개발 매니저가 브랜치를 도입하는 이유.
팀 개발시 팀 단위 개발 프로젝트를 효율적으로 관리할 수 있기 때문에 사용합니다.
팀원이 수정한 코드와 내가 작업한 코드가 겹치게 되면 충돌이 발생되는데, 이를 최소화 하기 위해 사용하는 목적도 있습니다.

개발이슈가 발생하면 이슈를 생성하고 해당 이슈로 브랜치를 만들어서 코드를 작성합니다.
main 스트림은 관리만 진행하고 직접 main 스트림에서 코드를 건드리지 않습니다.
실제 코드는 가급적 만들어진 branch에서만 작성해주세요.

브랜치명은 보통 아래 이름으로 많이 만들어집니다.

- 이슈 번호
- 버그 번호
- 패치 번호

```bash
git pull
git branch iss20
git checkout iss20
<< 코드 작성 >>
git checkout main
git pull origin main
```


#### 세부 교육 내용

- 협업을 위해 개발자끼리 약속해야할 것!: `우리 main stream은 건드리지 말자! 우리는 꼭 브런치를 만들고 각자의 개발자가 테스트하고 문제가 없을 때만 merge 하자~!`
- Github에서 branch 리스트 보는 방법: [OpenColorIO사례](https://github.com/AcademySoftwareFoundation/OpenColorIO)
- Git의 Content-addressable 파일 시스템 설명하기
- SHA1 알고리즘을 만들어지는 Key: 최신버전 확인 불필요, 중복 X, 오프라인 커밋 가능, 커밋시 부모의 HASH값도 저장
  - 찾아볼 자료1: https://spri.kr/posts/view/21757
  - 찾아볼 자료2: https://m.blog.naver.com/vjhh0712v/221453210356

| Key | Value |
| ------------- | ------------- |
| 5e1c4447a691fa0b687f502a65c3c1ff792033f9 | 변경사항만 저장 |


## Upstream setting

- 개발하고 싶은 리포지터리를 fork 합니다.
- fork 한 리포지터리를 clone 합니다.
- 사용예시

```bash
git remote add https://github.com/lazypic/OpenPipelineIO
```
