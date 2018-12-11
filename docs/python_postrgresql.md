# Python PostrgreSQL

## psycopg2 설치

PostgreSQL을 python을 이용해서 컨트롤할 때 가장 유명한 라이브러리는 psycopg2 입니다.
설치해보겠습니다.

```
# pip install psycopg2
# pip install psycopg2-binary
```

https://pypi.org/project/psycopg2/

## 테이블 생성
데이터를 넣기 위해서는 먼저 데이터를 넣을 테이블이 필요합니다.
테이블을 만드는 예제를 다루어 보겠습니다.


![struct](../figures/rdbms.png)

```python
#!/usr/bin/env python
import psycopg2
 
def create_tables():
    commands = (
        """
        CREATE TABLE shows (
            show_id SERIAL PRIMARY KEY,
            show_name VARCHAR(255) NOT NULL
        )
        """,
        """ CREATE TABLE users (
                user_id SERIAL PRIMARY KEY,
                user_name VARCHAR(255) NOT NULL
        )
        """,
        """
        CREATE TABLE show_extension (
                show_id INTEGER PRIMARY KEY,
                show_deadline VARCHAR(25),
                FOREIGN KEY (show_id)
                    REFERENCES shows (show_id)
                    ON UPDATE CASCADE ON DELETE CASCADE
        )
        """,
        """
        CREATE TABLE show_user (
                show_id INTEGER NOT NULL,
                user_id INTEGER NOT NULL,
                role VARCHAR(25),
                PRIMARY KEY (show_id , user_id),
                FOREIGN KEY (show_id)
                    REFERENCES shows (show_id)
                    ON UPDATE CASCADE ON DELETE CASCADE,
                FOREIGN KEY (user_id)
                    REFERENCES users (user_id)
                    ON UPDATE CASCADE ON DELETE CASCADE
        )
        """)
    conn = None
    try:
        # connect to the PostgreSQL server
        conn = psycopg2.connect(host="192.168.219.105",database="shows", user="postgres", password="postgres")
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

테이블이 잘 생성되어있는지 체크를 해봅시다.

```bash
# su – postgres
-bash-4.2$ psql -d shows
postgres=# \dt

            List of relations
 Schema |      Name      | Type  |  Owner   
--------+----------------+-------+----------
 public | show_extension | table | postgres
 public | show_user      | table | postgres
 public | shows          | table | postgres
 public | users          | table | postgres
(4 rows)

postgres=# \q
```

## 테이블에 데이터 추가
shows 테이블에 데이터를 추가해 보겠습니다.

```python
#!/usr/bin/env python
import psycopg2
 
def insert_show(show_name):
    sql = """INSERT INTO shows(show_name)
             VALUES(%s) RETURNING show_id;"""
    conn = None
    show_id = None
    try:
        conn = psycopg2.connect(host="192.168.219.105",database="shows", user="postgres", password="postgres")
        # create a new cursor
        cur = conn.cursor()
        # execute the INSERT statement
        cur.execute(sql, (show_name,))
        # get the generated id back
        show_id = cur.fetchone()[0]
        # commit the changes to the database
        conn.commit()
        # close communication with the database
        cur.close()
    except (Exception, psycopg2.DatabaseError) as error:
        print(error)
    finally:
        if conn is not None:
            conn.close()
    return show_id

if __name__ == '__main__':
    insert_show("circle")
```

## 테이블에서 데이터 가지고 오기
```python
#!/usr/bin/env python
import psycopg2

def get_shows():
    conn = None
    try:
        conn = psycopg2.connect(host="192.168.219.105",database="shows", user="postgres", password="postgres")
        cur = conn.cursor()
        cur.execute("""
            SELECT show_id, show_name
            FROM shows
            ORDER BY show_name;
        """)
        print("The number of shows: ", cur.rowcount)
        row = cur.fetchone()
 
        while row is not None:
            print(row)
            row = cur.fetchone()
        cur.close()
    except (Exception, psycopg2.DatabaseError) as error:
        print(error)
    finally:
        if conn is not None:
            conn.close()

if __name__ == '__main__':
    get_shows()
```

## 테이블에서 데이터 업데이트하기
```python
#!/usr/bin/env python
import psycopg2 

def update_show(show_id, show_name):
    sql = """ UPDATE shows
                SET show_name = %s
                WHERE show_id = %s"""
    conn = None
    updated_rows = 0
    try:
        conn = psycopg2.connect(host="192.168.219.105",database="shows", user="postgres", password="postgres")
        # create a new cursor
        cur = conn.cursor()
        # execute the UPDATE  statement
        cur.execute(sql, (show_name, show_id))
        # get the number of updated rows
        updated_rows = cur.rowcount
        # Commit the changes to the database
        conn.commit()
        # Close communication with the PostgreSQL database
        cur.close()
    except (Exception, psycopg2.DatabaseError) as error:
        print(error)
    finally:
        if conn is not None:
            conn.close()
 
    return updated_rows
if __name__ == '__main__':
    update_show("1","circle2")
```

## 테이블에서 데이터 삭제

```python
#!/usr/bin/env python
import psycopg2
 
def delete_show(show_id):
    conn = None
    rows_deleted = 0
    try:
        # read database configuration
        params = config()
        # connect to the PostgreSQL database
        conn = psycopg2.connect(**params)
        # create a new cursor
        cur = conn.cursor()
        # execute the UPDATE  statement
        cur.execute("DELETE FROM shows WHERE show_id = %s", (show_id,))
        # get the number of updated rows
        rows_deleted = cur.rowcount
        # Commit the changes to the database
        conn.commit()
        # Close communication with the PostgreSQL database
        cur.close()
    except (Exception, psycopg2.DatabaseError) as error:
        print(error)
    finally:
        if conn is not None:
            conn.close()
    return rows_deleted

if __name__ == '__main__':
    delete_show("1")
```

## Reference
http://www.postgresqltutorial.com/postgresql-python/connect/