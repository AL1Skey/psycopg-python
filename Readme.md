# Psycopg Python

Psycopg is python library that deal with postgreSQL

# How to use

```py
import psycopg2
#Open Connection
fumo = psycopg2.connect(host="localhost",dbname="postgres",user="postgres",password="123321",port="5432")

#Open Executable Access
acertain = fumo.cursor()

#Do SQL command here
acertain.execute("""--sql
CREATE TABLE IF NOT EXIST AcademyCityStudents(
    id INT PRIMARY KEY,
    name VARCHAR(255)
    age INT,
    gender CHAR,
    lvl FLOAT
)
""")

acertain.execute("""YOUR NEXT COMMAND HERE""")

acertain.execute("""RANDOM SQL COMMAND HERE""")
..........

#Execute all the SQL Command
acertain.commit()

#Close the Executable Access and Connection to Database
acertain.close()
fumo.close()
```

# How it works?

- Connect to database with psycopq2.connect() with defined host dbname user password and port
- Assign new variable as Executable Access of SQL Command on Connected database with .cursor()
- Use SQL command by save it on Executable Access
- Execute One or Multiple SQL Command with .commit()
- Close Executable Access and Database Access with .close()
