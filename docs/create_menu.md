# 뉴크 메뉴 등록하기

뉴크 상단에 Script 메뉴를 추가해보겠습니다.

## 이슈관리 페이지를 접근하는 메뉴 제작
개발을 하다보면 이슈관리가 중요합니다.
우리가 만들어야 할 기능, 이슈가 논의되는 페이지를 띄우는 메뉴와 기타 메뉴들을 만들어 보겠습니다.

menu.py
```python
import nukescripts
mb = menubar.addMenu("Lazypic")
mb.addCommand("Issue_and_Bugs", "nukescripts.start('https://github.com/lazypic/nuke/issues')")
mb.addCommand("Slack", "nukescripts.start('https://lazypic.slack.com')")
mb.addCommand("Clip Library", "nukescripts.start('https://www.youtube.com/channel/UC0L_YtB4PWSkOwp2m9587MA/playlists?view_as=subscriber')")
```

위 코드를 추가하고 잘 작동되는지 체크합니다.
위 주소는 제가 개발하고 있는 이슈 주소입니다. 위에 적힌 URL 대신 여러분이 개발하는 뉴크 리포지터리의 이슈페이지를 연결해보세요.
추후 여러분이 만들 github.io 페이지도 연결해보세요.

> 응용 : 회사, 팀에서 사용하는 웹서비스중에서 유용한 링크들을 연결해보세요.