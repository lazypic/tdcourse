# 왜 리눅스를 사용하는가?
한국 대규모 VFX회사 에서는 거의 대부분 리눅스 시스템을 사용한다.

## 리눅스를 사용하는 이유.
- 무료 : 비용절감
- 안정적
- 개발자 친화적. 인하우스 툴을 제작, 배포하기 편리하다.
- 수많은 개발도구를 무료로 사용할 수 있다.
- 컴퓨터 사양이 낮아도 효율이 좋다. 다른 OS보다 실제 연산이 10~15% 빠른 소프트웨어들이 존재합니다.
- 악성코드의 노출이 낮음.
- 대량셋팅이 용이함
- 네트워크 파일시스템 지원 : 회사가 경로를 셋팅하여 사용할 때 일괄적으로 통일해서 사용가능하다.
- 대량의 렌더팜, 서버 셋팅용이 : ssh, 가상화, 서버 매니징툴들이 많이 있습니다.
- 보안 : 소스코드가 공개되어있어서 비교적 빠른 보안업데이트가 나온다. 간혹 공개 소스를 분석하여 취약점을 이용하는 사용자도 있다. 보안뉴스를 조금 보면 크게 도움이 된다.

## CentOS를 사용하는 이유
- Autodesk, Foundry 에서 Redhat 계열의 리눅스에서 테스트합니다.
- Redhat은 Fedora에서 테스팅하여 만들어집니다.
- CentOS는 Redhat이 배포되면 같은 코드 그대로 사용됩니다.

#### CentOS의 특징
- https://www.lesstif.com/pages/viewpage.action?pageId=20775405

## 각 소프트웨어 요구사항 Reference
- Autodesk : https://knowledge.autodesk.com/support/maya/learn-explore/caas/sfdcarticles/sfdcarticles/System-requirements-for-Autodesk-Maya-2018.html
- Foundry Nuke : https://www.foundry.com/products/nuke/requirements
- Foundry Katana : https://www.foundry.com/products/katana/requirements