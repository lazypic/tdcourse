# Setuser
Zenity를 이용해서 사용자 환경변수 등록 프로그램을 제작해보겠습니다.

보통 작업전 최초 한번 실행하는 소프트웨어이기 때문에 많은 시간을 들이는 것이 때론 시간낭비가 될 수 있는 소프트웨어 입니다.

따라서 간단하게 Zenity를 이용하여 제작해 봅시다.

사용자 환경변수를 설정하고 사용하면 셋팅에 들인 시간에 대비해 개인PC뿐 아니라, 공용 PC, LDAP 설정된 컴퓨터도 동일한 환경에서 작업 할 수 있는 간편한 장점이 있습니다.

## 최종화면
아래 프로그램은 Lazypic에서 사용하는 setuser 명령어 입니다.

![setuser01](../figures/setuser01.png)
![setuser02](../figures/setuser02.png)
![setuser03](../figures/setuser03.png)
![setuser04](../figures/setuser04.png)
![setuser05](../figures/setuser05.png)
![setuser06](../figures/setuser06.png)
![setuser07](../figures/setuser07.png)
![setuser08](../figures/setuser08.png)

잘 설정되면 ~/.bashrc에 환경변수가 우리가 입력한 변수가 추가되어야 합니다.
![setuser09](../figures/setuser09.png)

프로그램을 다시 실행하면 기존 정보는 삭제되고 새로운 정보가 갱신되어야 합니다.


## 실습
- 위 인터페이스를 작성해봅시다.
- 환경변수만 삭제하는 unsetuser 명령어를 제작합니다.