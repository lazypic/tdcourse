# 데이터베이스
툴을 개발을 하다보면 어느 순간부터는 데이터의 검색 측면을 생각하고 데이터베이스를 활용해야겠다고 판단이 서는 순간이 다가옵니다. 많은 데이터베이스가 있지만 큰 사용법과 개념은 모두 비슷비슷 합니다.

- 데이터 넣기
- 데이터 수정
- 데이터 추출
- 데이터 삭제
- 데이터 검색

위 기능이 주요 기능이며, 나머지는 필요할 때 공부하고 실험해보면 됩니다. 너무 어렵게 생각하지 마세요.

주로 사용하는 DB는 아니지만 시장에서 자주 사용하는 DB에 대해서 설치법 기본적인 사용법만 익혀두더라도
추후 다른 솔루션을 설치 및 적용시 많은 도움이 됩니다.

## PostrgreSQL, MySQL
- 사용툴 : [Shotgun](https://support.shotgunsoftware.com/hc/en-us/articles/114094526153-Shotgun-security-white-paper), [Tactic](http://community.southpawtech.com/community/link/data_management), [Ftrack](https://help.ftrack.com/administering-ftrack/on-prem/handling-backups)

관계형 데이터베이스입니다.

회사에서 사용는 수많은 어플리케이션은 아마도 PostrgreSQL, MySQL을 많이 사용하게 됩니다. 익혀두면 실무를 진행할 때 굉장히 도움이 많이됩니다.

## MongoDB
Collection, Documents 베이스의 NoSQL입니다. 문서는 json으로 저장됩니다.
저는 개인적으로 프로젝트를 하면서 자료구조를 예측할 수 없고 초반에 설계 구조가 계속 바뀌는 프로젝트에 활용하고 있습니다.

아무래도 PostrgreSQL, MySQL처럼 RDBMS 방식의 DB보다는 확장, 설계유연성, 장애처리가 좀더 편리하기 때문에 초기 프로그램을 제작시 들이는 시간 및 비용이 상대적으로 RDBMS 데이터베이스보다 빠릅니다.

## Redis
Key, Value 값을 심플하게 저장하거나 불러올 때 사용하기 좋은 DB입니다.
프로덕션에서는 매일매일 생성되는 사용자의 데이터를 처리하기에 좋습니다.

## Reference
- https://www.youtube.com/watch?v=HQFreqPb3dg

## 실습
- 쉬운 Redis를 시작으로 MongoDB, MySQL을 설치 및 실습해보겠습니다.