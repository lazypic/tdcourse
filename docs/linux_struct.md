# 리눅스의 구조

우리가 컴퓨터를 켜면, 

1. 하드웨어에 전기가 들어갑니다.
1. 하드웨어에 이상이 없다면, 리눅스 커널이 실행됩니다.
1. OS에 필요한 프로세스들이 순서대로 실행됩니다.(System Call interface를 통해서..)
1. X-windows 가 실행되며 Desktop 화면이 띄워집니다.
1. Desktop에서 우리는 Shell(X-Windows용)을 띄웁니다.
1. 우리는 터미널을 열어서.. 우리가 필요한 소프트웨어(마야, 뉴크)를 실행시킵니다.

![linux_struct](https://i.stack.imgur.com/CtbMg.png)

우리가 리눅스 커널의 깊숙한 부분을 다루진 않지만, 컴파일러, Shell, Application Programs 부분은 항상 다루는 영역입니다.

자신이 앞으로 작성하는 코드가 OS 아키텍쳐의 어느 부분과 관련이 되어있는지 Layer층을 알고 무언가를 진행하는 것은 중요합니다.
