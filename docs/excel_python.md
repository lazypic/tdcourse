# 엑셀파일을 파이썬으로 처리하기
많은 프로젝트 매니징 파이프라인툴을 엑셀을 지원합니다.
프로젝트 초기에 프로젝트 매니징 툴을 사용할 수 없는 프로젝트 초기단계에서는 프로듀서, 메니저, 기획자들은 엑셀을 많이 사용하기 때문입니다.

보통 프로젝트 매니징 파이프라인툴은 .csv, .xlsx 파일을 지원하는 것이 필수가 되었습니다.

## LibreOffice 설치
리눅스에서는 Excel 대신 LibreOffice를 많이 사용합니다.
LibreOffice 엑셀을 설치해봅시다.

## 지원 예
- Shotgun : https://support.shotgunsoftware.com/hc/en-us/articles/219031188-How-to-import-an-existing-bid-sheet-to-create-Shots-and-Tasks
- Ftrack : https://www.youtube.com/watch?v=DBQvcj--1KM
- Tactic : https://github.com/Southpaw-TACTIC/Docs/blob/master/section/doc/tactic-end-user/end-user/importing-csv-data/index.txt

## Python 자주 사용하는 모듈

#### CSV 파서
python에는 csv 파서가 기본적으로 탑제 되어있습니다.

```python
import csv
```

#### Excel 파서

자주 사용하는 라이브러리를 일괄 설치합니다.
```
$ pip install --user openpyxl
$ pip install --user xlsxwriter
$ pip install --user xlrd
$ pip install --user xlwt
$ pip install --user xlutils
$ pip install --user pillow <- 엑셀에 이미지를 넣을 때 사용됩니다.
```

## .csv 파일 읽기

```python
#coding:utf8
import os
import csv
csvPath = os.path.expanduser("~/examples/csv/cglist.csv")
with open(csvPath) as csvFile:
    csvReader = csv.reader(csvFile, delimiter=',')
    for row in csvReader:
        print(row)
```

## .csv 파일 저장

```python
import csv

with open('/path/cglist.csv', mode='w') as csv_file:
    fieldnames = ['ep','seq', 'scene', 'shot', 'note']
    writer = csv.DictWriter(csv_file, fieldnames=fieldnames)
    writer.writeheader()
    writer.writerow({'ep':'1','seq': 'CAR', 'scene': 'FOO', 'shot': '0010', 'note': 'cg car'})
    writer.writerow({'ep':'1','seq': 'CAR', 'scene': 'FOO', 'shot': '0020', 'note': 'add dust'})
    writer.writerow({'ep':'1','seq': 'CAR', 'scene': 'BAR', 'shot': '0010', 'note': 'cg car, add dust'})
```

## .xlsx 파일 읽기

```python
#coding:utf8
import os
from openpyxl import load_workbook

xlsxPath = os.path.expanduser("~/examples/xlsx/cglist.xlsx")
wb = load_workbook(filename=xlsxPath, read_only=True)
ws = wb["Sheet1"]
for row in ws.rows:
    for cell in row:
        print(cell.value)
```

## .xlsx 파일 쓰기

```python
from openpyxl import Workbook
wb = Workbook()
dest  = 'output.xlsx'
ws1 = wb.active
ws1.title = "Sheet1"
ws1.append(["eq","seq","scene","shot","note"])
ws1.append(["1","CAR","FOO","0010","add cg car"])
ws1.append(["1","CAR","FOO","0020","add dust"])
ws1.append(["1","CAR","BAR","0010","add car, add dust"])
wb.save(filename = dest)
```

## 실습
- 리브레오피스를 설치하고 Excel 파일을 만들어서 저장하고 해당 파일로 테스트해봅시다.
- 엑셀파일을 직접 만들어보고 데이터를 로딩해보세요.

## Reference
- https://openpyxl.readthedocs.io/en/stable/usage.html
- https://openpyxl.readthedocs.io/en/stable/
- http://www.python-excel.org/
