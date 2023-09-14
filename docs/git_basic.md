# Git

Git은 버전 관리 시스템중 현재 가장 인기있는 툴입니다.
Git통해 코드를 버전관리 하게되면 에러에 대한 롤백, 협업이 가능해집니다.

<개념 구상도를 넣기>

## 윈도우즈 CRLF 에러 처리

warning: in the working copy of 'edit.sh', LF will be replaced by CRLF the next time Git touches it 에러 발생시 아래처럼 타이핑한다.

```bash
git config --global core.autocrlf true
```

## init
Git을 사용하기 위해서는 최초 셋팅이 필요합니다.
사용할 폴더로 들어가서 init 명령을 한번 실행해야 합니다.

```
$ git init
```

## clone

```bash
git clone https://github.com/lazypic/OpenPipelineIO
```


명령어를 치고 나면 폴더에 `.git` 이라는 숨김폴더가 생깁니다.
이 디렉토리 안에는 환경설정, Git 버전관리가 실제로 일어나는 경로입니다.

## add
add 명령어는 Git에게 버전 관리할 파일을 알려주는 역할을 합니다.

```
git add yourcode.go
```

- git add 하는 방법은 많이 있지만 차이점을 추후 구분하고 사용해주세요. : https://atrystwithprogramming.wordpress.com/tag/git-add-vs-git-add/

## commit

commit 명령어는 코드를 수정하고 메모를 하는 기능입니다.
최대한 잘 작성하면 나중에 코드를 돌릴 때 편하니 자세히 적는 습관을 들여주세요.
이 내용은 추후 github를 사용했을 때 자동으로 올라가는 내용이니 여러분의 지성을 뽐내주세요.

```bash
git commit -m "나는 이러이러한것을 코드에 추가했다."
```

## push

```bash
git push origin main
```

## branch

branch 단계 처리하기

```bash
git branch iss01
git checkout iss01
git add edit.go
git commit -m "edit file"
git push origin iss01
pull request
code review
merge
git checkout main
git pull origin main
```

## 나머지 명령어들에 대해서..
사실 Git은 초심자에게 조금 복잡하지만,
나머지 명령어는 협업을 하거나 Github를 연동하면서 천천히 배워간다면 그리 어렵지 않습니다.
상황이 발생했을 때 같이 익혀갑시다.

## Reference
- Git 을 소개하는 자료중 [Pro Git](https://progit2.s3.amazonaws.com/ko/2015-07-08-5c390/progit-ko.582.pdf) E-book이 가장 유명합니다.
