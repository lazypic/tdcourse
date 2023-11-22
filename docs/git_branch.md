# Git branch

## Branch

Git branch 관리에 대해 설명합니다.

![gitbranch](../figures/gitbranch.png)

개발이슈가 발생하면 이슈를 생성하고 해당 이슈로 브랜치를 만들어서 코드를 작성합니다.
main 스트림은 관리만 직접 건드리지 않습니다.
실제 코드는 가급적 만들어진 branch에서만 작성해주세요.

```bash
git pull
git branch iss20
git checkout iss20
<< 코드 작성 >>
git checkout main
git pull origin main
```

## Upstream

- 개발하고 싶은 리포지터리를 fork 합니다.
- fork 한 리포지터리를 clone 합니다.
- git remote add https://github.com/lazypic/OpenPipelineIO
