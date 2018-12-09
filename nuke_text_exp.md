# Nuke Expression Text+
텍스트 노드에서도 뉴크 익스프레션을 사용할 수 있습니다.
Text노드에서 자주 사용되는 익스프레션을 실습해 보겠습니다.

![text_message](figures/text_message.png)

프레임 표기
```
[frame]
```

프레임 포멧팅
```
[format %04d [frame]]
```

현재 뉴크파일 씬파일 이름 표기
```
[value root.name]
```

## Metadata
회사, 조직 파이프라인 내에서는 .exr 이미지에 필요한 메타데이터를 담아 다음 팀에 많이 전달합니다.
데이터에 정보를 자유롭게 담을 수 있어서 편리한 방법이기도 합니다.
이 메타데이터 정보를 출력해야하거나 값을 이용해야할 때 유용한 익스프레션입니다.

메타데이터라고 타이핑하면 모든 metadata를 출력합니다.
```
[metadata]
```

메타데이터중 key값을 입력하면 해당 value값이 출력됩니다.
```
[metadata arri/camera/CameraClipName]
```

## 환경변수
환경변수를 가지고 오는 방법은 콘텐츠 제작 파이프라인에서 자주 사용되는 방법입니다.
아래처럼 환경변수를 불러올 수 있습니다.

USER 환경변수를 가지고 오는 예
```
[python os.getenv('USER')]
```


## Reference
- https://learn.foundry.com/nuke/8.0/content/user_guide/effects/entering_text.html
- 날짜처리 : http://www.tcl.tk/man/tcl8.5/tutorial/Tcl41.html