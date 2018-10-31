# Zenity
단순한 프로그램에 GUI를 처리해야하는 상황이라면 zenity를 추천합니다.
우리는 간혹 단순한 스크립트에 복잡한 GUI를 입히는 경우를 볼 수 있습니다.
유지보수 측면에서도 굉장히 비효율적입니다.

여러분의 스크립트가 단순하다면 단순한 GUI Zenity를 사용해보세요.

### 사용법
- 진행률 처리
```
cp -rf ./src/images/*.exr /dst | tee >(zenity --progress --pulsate)
```
| tee 명령어는 stdout을 화면과 파일로 동시에 출력하는 리눅스 명령어 입니다.

- 선택창
```
ans=$(zenity  --list  --text "어떤색을 좋아해요?" --checklist  --column "선택" --column "옵션" FALSE "흰색" TRUE "검정" --separator=":"); echo $ans
```
