# 데이터베이스

모든 데이터베이스의 개념은 비슷합니다.

- 데이터 넣기
- 데이터 수정
- 데이터 가지고오기
- 데이터 삭제

나머지는 정보를 이용해서 응용하는 것 뿐입니다. 너무 어렵게 생각하지 마세요.

일반적인 DB설명은 DB책을 보면 자세히 나와있습니다. 저는 약간 실무적인 관점에서 DB를 설명하겠습니다.

## PostrgreSQL
- 사용툴 : [Shotgun](https://support.shotgunsoftware.com/hc/en-us/articles/114094526153-Shotgun-security-white-paper), [Tactic](http://community.southpawtech.com/community/link/data_management)

## MySQL
- 사용툴 : [Ftrack](https://help.ftrack.com/administering-ftrack/on-prem/handling-backups)

## MongoDB
collection, documents 베이스의 NoSQL입니다. 문서는 json으로 저장됩니다.
저는 개인적으로 프로젝트를 하면서 자료구조를 예측할 수 없고 초반에 설계 구조가 계속 바뀌는 프로젝트에 자주 활용한 사례가 있습니다.

## Redis
key, value 값을 심플하게 저장하거나 불러올 때 사용하기 좋은 DB입니다.
매일매일 생성되는 사용자의 임시 데이터를 처리하기에 좋습니다.

