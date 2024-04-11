# Tasks Project

## 0. Regex-ing

### Description
Write a function called `filter_datum` that returns the log message obfuscated.

### Arguments
- `fields`: a list of strings representing all fields to obfuscate
- `redaction`: a string representing by what the field will be obfuscated
- `message`: a string representing the log line
- `separator`: a string representing by which character is separating all fields in the log line (message)

The function should use a regex to replace occurrences of certain field values.
`filter_datum` should be less than 5 lines long and use `re.sub` to perform the substitution with a single regex.

Example:
```python
fields = ["password", "date_of_birth"]
messages = ["name=egg;email=eggmin@eggsample.com;password=eggcellent;date_of_birth=12/12/1986;", "name=bob;email=bob@dylan.com;password=bobbycool;date_of_birth=03/04/1993;"]

for message in messages:
    print(filter_datum(fields, 'xxx', message, ';'))
```

Output:
```
name=egg;email=eggmin@eggsample.com;password=xxx;date_of_birth=xxx;
name=bob;email=bob@dylan.com;password=xxx;date_of_birth=xxx;
```

## 1. Log formatter

### Description
Update the `RedactingFormatter` class to accept a list of strings `fields` constructor argument.

Implement the `format` method to filter values in incoming log records using `filter_datum`. Values for fields in `fields` should be filtered.

DO NOT extrapolate `FORMAT` manually. The `format` method should be less than 5 lines long.

Example:
```python
import logging

RedactingFormatter = __import__('filtered_logger').RedactingFormatter

message = "name=Bob;email=bob@dylan.com;ssn=000-123-0000;password=bobby2019;"
log_record = logging.LogRecord("my_logger", logging.INFO, None, None, message, None, None)
formatter = RedactingFormatter(fields=("email", "ssn", "password"))
print(formatter.format(log_record))
```

Output:
```
[HOLBERTON] my_logger INFO 2019-11-19 18:24:25,105: name=Bob; email=***; ssn=***; password=***;
```

## 2. Create logger

### Description
Implement a `get_logger` function that returns a `logging.Logger` object.

The logger should be named "user_data" and only log up to `logging.INFO` level. It should not propagate messages to other loggers. It should have a `StreamHandler` with `RedactingFormatter` as formatter.

Create a tuple `PII_FIELDS` constant at the root of the module containing the fields from `user_data.csv` that are considered PII. `PII_FIELDS` can contain only 5 fields - choose the right list of fields that are considered as “important” PIIs or information that you must hide in your logs. Use it to parameterize the formatter.

## 3. Connect to secure database

### Description
Implement a `get_db` function that returns a connector to the database (`mysql.connector.connection.MySQLConnection` object).

Use the `os` module to obtain credentials from the environment.
Use the module `mysql-connector-python` to connect to the MySQL database (`pip3 install mysql-connector-python`).

Example:
```python
db = get_db()
cursor = db.cursor()
cursor.execute("SELECT COUNT(*) FROM users;")
for row in cursor:
    print(row[0])
cursor.close()
db.close()
```

## 4. Read and filter data

### Description
Implement a `main` function that takes no arguments and returns nothing.

The function will obtain a database connection using `get_db` and retrieve all rows in the users table and display each row under a filtered format.

Example Output:
```
[HOLBERTON] user_data INFO 2019-11-19 18:37:59,596: name=***; email=***; phone=***; ssn=***; password=***; ip=e848:e856:4e0b:a056:54ad:1e98:8110:ce1b; last_login=2019-11-14T06:16:24; user_agent=Mozilla/5.0 (compatible; MSIE 9.0; Windows NT 6.1; WOW64; Trident/5.0; KTXN);
```

Filtered fields:
- name
- email
- phone
- ssn
- password

Only your `main` function should run when the module is executed.

## 5. Encrypting passwords

### Description
Implement a `hash_password` function that expects one string argument named `password` and returns a salted, hashed password, which is a byte string.

Use the `bcrypt` package to perform the hashing (with `hashpw`).

Example:
```python
password = "MyAmazingPassw0rd"
print(hash_password(password))
```

## 6. Check valid password

### Description
Implement an `is_valid` function that expects 2 arguments and returns a boolean.

Arguments:
- `hashed_password`: bytes type
- `password`: string type

Use `bcrypt` to validate that the provided password matches the hashed password.

Example:
```python
password = "MyAmazingPassw0rd"
encrypted_password = hash_password(password)
print(encrypted_password)
print(is_valid(encrypted_password, password))
```
