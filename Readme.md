# Psycopg Python

Psycopg is python library that deal with postgreSQL

# How to use

```py
import psycopg2
#Open Connection
fumo = psycopg2.connect(host="localhost",dbname="postgres",user="postgres",password="123321",port="5432")

#Open Executable Access
acertain = fumo.cursor()


try:
    #Do SQL command here
    acertain.execute("""--sql
    CREATE TABLE IF NOT EXIST AcademyCityStudents(
        id INT PRIMARY KEY,
        name VARCHAR(255)
        age INT,
        gender CHAR,
        lvl FLOAT
    );
    """)

    acertain.execute("""YOUR NEXT COMMAND HERE""")

    acertain.execute("""RANDOM SQL COMMAND HERE""")
    ..........

    #Execute all the SQL Command
    fumo.commit()
except Exception as e:
    #If error, Rollback to previous checkpoint
    acertain.execute("""ROLLBACK;""")
    fumo.commit()

#Close the Executable Access and Connection to Database
acertain.close()
fumo.close()
```

# How it works?

- Connect to database with psycopq2.connect() with defined host dbname user password and port to variable

```py
fumo = psycopg2.connect(host="localhost",dbname="postgres",user="postgres",password="123321",port="5432")
```

- Assign new variable as Temporary Storage contain Executable Command of SQL Command on Connected database with .cursor()

```py
acertain = fumo.cursor()
```

- Use SQL command by save it on Executable Access with .execute()

```py
try:
    acertain.execute("""--sql
        CREATE TABLE IF NOT EXIST AcademyCityStudents(
            id INT PRIMARY KEY,
            name VARCHAR(255)
            age INT,
            gender CHAR,
            lvl FLOAT
        );
        """)
```

- Execute One or Multiple SQL Command with .commit() on connected database (psycopg2.connect())

```py
fumo.commit()
```

- If error occur on SQL side, rollback to checkpoint using .execute("""ROLLBACK"""); command

```py
except Exception as e:
    #If error, Rollback to previous checkpoint
    acertain.execute("""ROLLBACK;""")
    fumo.commit()
```

- Close Executable Access and Database Access with .close()

```py
acertain.close()
fumo.close()
```
