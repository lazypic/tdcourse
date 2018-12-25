# 엑셀파일을 파이썬으로 처리하기
많은 프로젝트 매니징 파이프라인툴을 엑셀을 지원합니다.
프로젝트 초기에 프로젝트 매니징 툴을 사용할 수 없는 프로젝트 초기단계에서는 프로듀서, 메니저, 기획자들은 엑셀을 많이 사용하기 때문입니다.

따라서 일반적으로 프로젝트 매니징 파이프라인툴은 .xlex, .csv 파일등을 지원하는 것이 필수가 되었습니다.

## LibreOffice 설치
리눅스에서는 Excel대신 LibreOffice를 많이 사용합니다.

## 지원 예
- Shotgun : https://support.shotgunsoftware.com/hc/en-us/articles/219031188-How-to-import-an-existing-bid-sheet-to-create-Shots-and-Tasks
- Ftrack : https://www.youtube.com/watch?v=DBQvcj--1KM
- Tactic : https://github.com/Southpaw-TACTIC/Docs/blob/master/section/doc/tactic-end-user/end-user/importing-csv-data/index.txt

## Python으로 핸들링하기

#### CSV 파서
- https://realpython.com/python-csv/

#### Excel 파서

```
pip install openpyxl
pip install xlsxwriter
pip install xlrd
pip install xlwt
pip install xlutils
pip install pillow <- 엑셀에 이미지를 넣을 때 사용됩니다.
```

## 실습
- 엑셀파일을 직접 만들어보고 데이터를 로딩해보세요.

## Reference
- http://www.python-excel.org/