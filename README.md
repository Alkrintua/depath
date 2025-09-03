# 📊 Data Engineering Learning Repository

Це мій особистий навчальний репозиторій для опанування **Data Engineering**.  
Тут я збираю:
- конспекти з теорії (DWH, OLTP/OLAP, ETL, моделювання даних),
- приклади коду (Spark, Airflow, Kafka),
- невеликі pet-проєкти для практики.

---

## 📂 Структура репозиторію

- `theory/` — конспекти та нотатки (Markdown-файли з поясненнями).
- `spark/` — приклади роботи з Apache Spark (PySpark jobs, трансформації).
- `airflow/` — прості DAG-и для оркестрації процесів.
- `kafka/` — базові приклади producer/consumer.
- `projects/` — невеликі pet-проєкти, які демонструють практику end-to-end.
- `README.md` — цей файл.

---

## 🚀 Приклади проєктів

### Spark CSV Aggregation
- **Мета:** обробка великого CSV (10 млн рядків), агрегація та запис у Parquet.
- **Технології:** PySpark, Parquet.
- **Результат:** прискорена обробка даних у порівнянні з pandas.

### Airflow Simple DAG
- **Мета:** оркестрація завдання `CSV → SQLite`.
- **Технології:** Airflow, Docker.
- **Результат:** базове розуміння DAG-структури.

---

## 📖 Конспекти

- [ERD та нормалізація даних](theory/erd-normalization.md)  
- [OLTP vs OLAP](theory/oltp-vs-olap.md)  
- [Data Warehouse: факти та виміри](theory/dwh-facts-dimensions.md)  
- [ETL vs ELT](theory/etl-vs-elt.md)