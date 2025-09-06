# 📊 Data Engineering Learning Repository

Це мій особистий навчальний репозиторій для опанування **Data Engineering**.  
Тут я збираю:
- конспекти з теорії (бази даних, DWH, архітектури),
- приклади коду (Spark, Airflow, Kafka),
- посилання на корисні ресурси,
- невеликі pet-проєкти для практики.

---

## 🛠️ План вивчення

### 🖥️ Linux & Bash
- базові утиліти (ls, cd, cat, grep, awk, sed)  
- робота з файлами та правами доступу  
- мережеві команди (curl, wget, netstat)  
- Docker basics (контейнери, docker-compose)  

### 🏛️ Data Warehouse & Data Lake (Теорія)
- OLTP vs OLAP  
- Архітектура DWH (Kimball / Inmon / Lakehouse)  
- Data Lakehouse (Iceberg, Delta, Hudi)  
- Batch-обробка, Lambda- та Kappa-архітектури  

### 📐 Моделювання даних
- Нормальні форми (1NF, 2NF, 3NF, BCNF)  
- ER-діаграми  
- Dimensional modeling  
- Star / Snowflake schema  
- Slowly Changing Dimensions (SCD)  

### 📑 Оптимізація зберігання
- Індекси (кластеризовані / некластеризовані)  
- Partitioning і clustering таблиць  
- Performance considerations  

### 🦆 Data Storage (DuckDB / MotherDuck / Iceberg)
- Локальний рушій DuckDB  
- MotherDuck як хмарне рішення  
- Iceberg tables: snapshots, partitioning, schema evolution  
- Snowflake & BigQuery basics  
- S3 / GCS як базове сховище  

### 🔄 Data Ingestion
- Airbyte (налаштування конекторів)  
- dlt (Python-first ingestion)  
- Fivetran (огляд як SaaS-альтернатива)  

### 🧩 Data Transformation
- dbt (моделі, тести, документація)  
- SQL Mesh (огляд альтернативи)  
- Pandas / Polars для аналітичних трансформацій  
- PySpark для масивних batch-завдань  

### ⚙️ Data Orchestration
- Airflow (DAG структура, operators, schedulers)  
- Prefect (flow-based orchestration)  
- Dagster (asset-based orchestration)  

### 📊 Serving & Reverse ETL
- Побудова marts (золота зона)  
- Star schema для BI  
- Hightouch (reverse ETL концепт)  

### ✅ Data Quality & Security
- dbt tests (unique, not_null, accepted_values, freshness)  
- Data contracts та SLA  
- Secrets management (env, Airflow Connections)  
- IAM політики та доступи до S3 / BigQuery / Snowflake  
- Маскування чутливих даних  

---

### 📝 Мови програмування
- **SQL**: аналітичні запити, DDL/DML, оптимізація  
- **Python**: pandas, polars, PySpark, dlt  
- **Bash**: shell-скрипти, автоматизація, інтеграція з Docker  


## 🔗 Корисні посилання

- [Data Engineering Book — Databases](https://github.com/oleg-agapov/data-engineering-book/blob/master/book/2-beginner-path/2-1-databases/databases.md)  
- [Exasol — Data Warehouse Basics](https://www.exasol.com/hub/data-warehouse/concepts-basics/)  
- [Spark Cluster repository](https://github.com/halltape/HalltapeSparkCluster/tree/main)
- [dbt-duckdb](https://github.com/dbt-labs/jaffle_shop_duckdb)
- https://github.com/pipelinetoinsights/elt-pipeline-with-dlt-and-dbt
- https://github.com/bytewax/awesome-public-real-time-datasets
---

## 📅 Roadmap

- [ ] Основи Linux та робота з CLI  
- [ ] Теорія DWH (OLTP, OLAP, архітектури)  
- [ ] ERD та моделювання даних  
- [ ] Нормалізація та індекси  
- [ ] Spark: перший проєкт (CSV → Parquet)  
- [ ] Airflow: DAG для завантаження даних  
- [ ] Kafka: простий producer/consumer приклад  
- [ ] Hadoop: базовий конспект  

---

## ✍️ Контакти

- **Автор:** Oleksandr Kryvoshei  
- **LinkedIn:** [linkedin.com/in/...](https://www.linkedin.com/in/oleksandr-kryvoshei-b28b30237/)  







