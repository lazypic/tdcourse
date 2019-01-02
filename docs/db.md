# 데이터베이스
툴을 개발을 하다보면 어느 순간부터는 효율성을 위해서 데이터베이스를 사용해야겠다고 판단이 서는 순간이 다가옵니다. DB는 사용법과 개념이 모두 비슷비슷 합니다.

- 데이터 넣기
- 데이터 수정
- 데이터 추출
- 데이터 삭제

나머지는 정보를 얻고 공부하고 응용하는 것 뿐입니다. 너무 어렵게 생각하지 마세요.

일반적인 DB설명은 DB책을 보면 자세히 나와있습니다. 저는 약간 실무적인 관점에서 DB를 설명하겠습니다.

## PostrgreSQL, MySQL
- 사용툴 : [Shotgun](https://support.shotgunsoftware.com/hc/en-us/articles/114094526153-Shotgun-security-white-paper), [Tactic](http://community.southpawtech.com/community/link/data_management), [Ftrack](https://help.ftrack.com/administering-ftrack/on-prem/handling-backups)


회사에서 사용는 수많은 어플리케이션은 아마도 PostrgreSQL, MySQL을 많이 사용하게 됩니다. 익혀두면 실무를 진행할 때 굉장히 도움이 많이됩니다.

## MongoDB
Collection, Documents 베이스의 NoSQL입니다. 문서는 json으로 저장됩니다.
저는 개인적으로 프로젝트를 하면서 자료구조를 예측할 수 없고 초반에 설계 구조가 계속 바뀌는 프로젝트에 자주 활용한 사례가 있습니다.

아무래도 PostrgreSQL, MySQL처럼 RDBMS 방식의 DB보다는 확장, 설계유연성, 장애처리가 좀더 편리하기 때문에 초기 프로그램을 제작시 들이는 시간 및 비용이 상대적으로 RDBMS 데이터베이스보다 빠릅니다.

## Redis
Key, Value 값을 심플하게 저장하거나 불러올 때 사용하기 좋은 DB입니다.
프로덕션에서는 매일매일 생성되는 사용자의 데이터를 처리하기에 좋습니다.

## Reference
- https://www.youtube.com/watch?v=HQFreqPb3dg