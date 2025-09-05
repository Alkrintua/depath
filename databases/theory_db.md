https://www.youtube.com/watch?v=WYV8hvJOAQE&list=WL&index=1

# 🦆 DuckDB Setup — Шпаргалка

## 🔹 Встановлення
```bash
pip install duckdb          # Python
conda install -c conda-forge duckdb   # Conda
duckdb                      # CLI
```

🔹 Підключення

import duckdb

# Пам’ять (тимчасова БД)
con = duckdb.connect()

# На диску (постійна БД)
con = duckdb.connect("my_database.db")

🔹 Основні команди

# SQL-запити
con.execute("CREATE TABLE people (id INT, name VARCHAR)")
con.execute("INSERT INTO people VALUES (1, 'Oleksandr')")

# Отримати результат як Pandas DataFrame
df = con.execute("SELECT * FROM people").df()

🔹 Робота з файлами

# Читання
con.execute("SELECT * FROM 'data.csv'").df()
con.execute("SELECT * FROM 'data.parquet'").df()

# Експорт
con.execute("COPY people TO 'people.csv' (HEADER, DELIMITER ',')")

🔹 Особливості

    In-process (як SQLite)

    Оптимізований для OLAP

    Працює напряму з CSV/Parquet

    Інтегрується з Pandas / Polars

- **In-Memory**  
  DuckDB зберігає дані за замовчуванням у пам’яті (`:memory:`).

- **File Format**  
  Має власний файловий формат (`.duckdb`), що дозволяє зберігати базу на диску.  
  ```python
  con = duckdb.connect("my_database.duckdb")

    ATTACH
    Використовується для підключення інших баз даних.

ATTACH 'other.duckdb' AS other_db;

COPY
Команда для експорту даних у зовнішні формати (CSV, Parquet тощо).

COPY my_table TO 'export.csv' (HEADER, DELIMITER ',');
COPY my_table TO 'export.parquet' (FORMAT 'parquet');
