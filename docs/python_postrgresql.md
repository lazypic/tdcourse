# Python PostrgreSQL

## psycopg2 설치

PostgreSQL을 python을 이용해서 컨트롤할 때 가장 유명한 라이브러리는 psycopg2 입니다.
설치해보겠습니다.

```
# pip install psycopg2
```

https://pypi.org/project/psycopg2/

## 테이블 생성
데이터를 넣기 위해서는 먼저 데이터를 넣을 테이블이 필요합니다.
테이블을 만드는 예제를 다루어 보겠습니다.

![table](http://www.postgresqltutorial.com/wp-content/uploads/2016/06/PostgreSQL-Python-Sample-Database-Diagram.png)
```
shows=# \dt
             List of relations
 Schema |     Name      | Type  |  Owner
--------+---------------+-------+----------
 public | part_drawings | table | postgres
 public | parts         | table | postgres
 public | vendor_parts  | table | postgres
 public | vendors       | table | postgres
(4 rows)
```

```python
#!/usr/bin/env python
 
import psycopg2
from config import config
 
def create_tables():
    commands = (
        """
        CREATE TABLE vendors (
            vendor_id SERIAL PRIMARY KEY,
            vendor_name VARCHAR(255) NOT NULL
        )
        """,
        """ CREATE TABLE parts (
                part_id SERIAL PRIMARY KEY,
                part_name VARCHAR(255) NOT NULL
                )
        """,
        """
        CREATE TABLE part_drawings (
                part_id INTEGER PRIMARY KEY,
                file_extension VARCHAR(5) NOT NULL,
                drawing_data BYTEA NOT NULL,
                FOREIGN KEY (part_id)
                REFERENCES parts (part_id)
                ON UPDATE CASCADE ON DELETE CASCADE
        )
        """,
        """
        CREATE TABLE vendor_parts (
                vendor_id INTEGER NOT NULL,
                part_id INTEGER NOT NULL,
                PRIMARY KEY (vendor_id , part_id),
                FOREIGN KEY (vendor_id)
                    REFERENCES vendors (vendor_id)
                    ON UPDATE CASCADE ON DELETE CASCADE,
                FOREIGN KEY (part_id)
                    REFERENCES parts (part_id)
                    ON UPDATE CASCADE ON DELETE CASCADE
        )
        """)
    conn = None
    try:
        # read the connection parameters
        params = config()
        # connect to the PostgreSQL server
        conn = psycopg2.connect(**params)
        cur = conn.cursor()
        # create table one by one
        for command in commands:
            cur.execute(command)
        # close communication with the PostgreSQL database server
        cur.close()
        # commit the changes
        conn.commit()
    except (Exception, psycopg2.DatabaseError) as error:
        print(error)
    finally:
        if conn is not None:
            conn.close()
 
 
if __name__ == '__main__':
    create_tables()
```

## 테이블에 데이터 추가

## 테이블 데이터 수정

## 테이블에서 데이터 가지고 오기

## 테이블에서 데이터 삭제

## Reference
http://www.postgresqltutorial.com/postgresql-python/connect/