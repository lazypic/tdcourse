# 기타 설정에 자주 사용되는 파일들
많은 툴에서 설정파일로 사용되는 기타 파일들을 알아보겠습니다.

자신이 만든 프로그램의 설정파일을 저장해야하는 상황은 소프트웨어를 설계하며 자주 발생됩니다.
이때 자신만의 포멧을 만들기 보다는 다른 프로그래머들이 쉽게 해당 설정 데이터를 가져다 사용할 수 있도록
범용 포멧으로 저장하는 것을 추천합니다.
또한 많은 툴들이 이미 범용 포멧을 사용하여 저장하고 있습니다.

자주사용하는 범용파일을 다루어 보겠습니다.

## Json
JavaScript Object Notation 의 약자입니다.

파일의 구조는 단순합니다. 정보는 보통 아래처럼 구성되어있습니다.
컴퓨터, 사람 모두 읽기 쉽다는 점이 좋습니다.

data.json
```json
{
    "project" : "circle",
    "shots" : ["FOO_0010","BAR_0010"],
}
```

test.py
```python
import json

with open('data.json') as f:
    data = json.load(f)

print(data)
```

- mongoDB 데이터 형식에 사용됩니다.
- Aamazon Web Service 설정시 사용됩니다.
- restAPI
- 추후 개발툴이 확장되어 미래에 웹과 연동을 생각한다면 이 포멧을 설정파일로 사용하면 좋습니다.

파이썬 파서 : https://stackabuse.com/reading-and-writing-json-to-a-file-in-python/

## Xml
Extensible Markup Language 의 약자입니다.
html언어 처럼 이미 약속된 tag를 사용하는 것이 아닌, 사용자가 원하는 tag를 지정하여 사용할 수 있습니다.

파일의 구조는 아래 구조를 띕니다.
파일을 저장하게되면 데이터보다 태그의 양이 상대적으로 더 많기 때문에 데이터 저장의 효율성적인 측면에서 꼭 Xml을 써야하는 상황이 아니라면 저는 잘 사용하지 않습니다.

data.xml
```xml
<?xml version="1.0" encoding="UTF-8"?>
<info>
    <project>
        <name>circle</name>
    </project>
    <shots>
        <item>
            <name>FOO_0010</name>
        </item>
        <item>
            <name>BAR_0010</name>
        </item>
    </shots>
</info>
```

test.py
```python
#!/usr/bin/env python
import xml.etree.ElementTree

root = xml.etree.ElementTree.parse("data.xml")

for e in root.findall("shots"):
    for sube in e.findall("item"):
        print sube.findtext("name")
```

- Katana SceneGraphXml에 사용됩니다. : https://learn.foundry.com/katana/current/Content/ug/scene_data/scenegraphxml.html

- FinalCutPro 편집파일 : https://developer.apple.com/library/archive/documentation/FinalCutProX/Reference/FinalCutProXXMLFormat/Introduction/Introduction.html

파이썬 파서 : https://docs.python.org/2/library/xml.etree.elementtree.html

## INI
ini initialization의 약자입니다.
보통 설정파일에 대한 비공식 표준형태의 포멧입니다.
`[ ]`로 감싸 있는 것은 세션입니다.
세션 하위에는 `키 = 값` 으로 데이터를 저장할 수 있습니다.
다양한 형의 자료구조를 저장하기에는 무리가 있지만, 그래도 가독성이 좋기 때문에 단순한 설정파일에 많이 사용되는 포멧입니다.

data.ini
```ini
[project]
name=circle
deadline="2020.01.13"

[shots]
name=FOO_0010,BAR_0010
```

test.py
```python
#!/usr/bin/env python
import ConfigParser

ini = ConfigParser.ConfigParser()
ini.read("data.ini")

print ini.sections()
print ini.options("project")
print ini.get("project","name")
```

- 윈도우즈 설정파일 쪽에서 자주 사용되는 포멧입니다.
- Unreal 프로젝트 설정에 사용됩니다.

python파서 : https://docs.python.org/3/library/configparser.html

## 기타
- 위에 나열한 파일 이외에도 .yml 파일도 자주 사용됩니다.
- .cfg, .conf 이름의 확장자 이지만 실제로 에디터에서 파일을 열어보면 .ini, .json, .xml 형태의 파일구조를 자주 사용하기도 합니다.

## 설정파일의 위치
리눅스에서는 일반적으로 설정파일을 홈디렉토리에 저장합니다.
`~/.프로그램명` 이름으로 자주 사용됩니다.

아래 명령어들을 타이핑하여 이미 존재하는 설정파일들을 관찰해 보세요.
```
cd ~
ls -al
```

여러분도 앞으로 여러분의 프로그램을 만들게 될 것 입니다.
이미 수많은 프로그램들이 따르고 있는 일반화된 규칙을 따르면 다른 개발자 및 사용자들이 이해하기 쉽습니다.