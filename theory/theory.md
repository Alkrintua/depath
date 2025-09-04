# Big Data & Cloud general theory

## Public cloud major players and comparison

Amazon Web Services (AWS) is an expanding, comprehensive, cloud computing platform provided by Amazon. In total, these cloud computing web services deliver a number of distributed computing building blocks and tools together with abstract primitive technical infrastructure. Amazon Elastic Compute Cloud is one of these services. It provides an opportunity for users to access a virtual cluster of computers at any time they need through the network. AWS's version of virtual computers is responsible for emulating most of a real computer's attributes, including graphics processing units (GPUs) and hardware central processing units (CPUs) for processing, hard-disk/SSD storage, local/RAM memory, networking, a choice of operating systems, and pre-loaded application software, such as customer relationship management (CRM), databases, and web servers.

Storage: Simple Storage Service (S3), Elastic Block Storage (EBS), Elastic File System (EFS), Storage Gateway, Snowball, Snowball Edge, Snowmobile.
Database: Aurora, RDS, DynamoDB, ElasticCache, Redshift, Neptune, Database migration service.
Backup Services: Glacier.

Microsoft Azure is a cloud computing service designed by Microsoft and meant for managing, building, testing, and deploying services and applications by Microsoft-managed data centers. It provides Platform as a Service (PaaS), Software as a Service (SaaS) and Infrastructure as a Service (IaaS) and supports a range of various programming languages, frameworks, and tools, including both third-party and Microsoft-specific and systems and software.

Storage: Blob Storage, Queue Storage, File Storage, Disk Storage, Data Lake Storage.
Database: SQL Database, Database for MySQL, Database for PostgreSQL, Data Warehouse, Server Stretch Database, Cosmos DB, Table storage, Redis cache, Data Factory.
Backup Services: Archival Storage, Recovery backups, Site recovery.

Google Cloud Platform (GCP) is a suite of cloud computing services provided by Google. It runs on the same infrastructure as the corporation uses internally for its end-user products like Gmail, Google Search, and YouTube. Together with various management tools, it provides a set of modular cloud services, including data storage, computing, machine learning and data analytics. To register, it requires either bank account details or a credit card.

Storage: Cloud Storage, Persistent Disk, Transfer appliance, Transfer Service.
Database: Cloud SQL, Cloud Bigtable, Cloud Spanner, Cloud Datastore.
Backup Services: Nearline (frequently accessed data), Coldline (infrequently accessed data).

## What is data modeling?

Data modeling refers to the process of creating a visual representation of the places where an application or software stores information, as well as how these sources of data interact with each other. Simply put, data modeling illustrates how data storage is organized.

Depending on the design, data modeling occurs on three levels—conceptual, logical, and physical. Each level has a different purpose and target audience. When creating a data model, you typically go from top to bottom: from drafting a data model outline based on business needs and requirements to designing a database.

1. Conceptual. This is a high-level data model that does not include implementation details. At this level, your data model won't contain granular information. For now, you are most interested in a detailed description of entity types, relationships, and constraints.
2. Logical. This level of data modeling is implemented using a commercial DBMS. The logical level is the mapping step between the conceptual model and the implementation data model for the DBMS being used on the project.
3. Physical. This is the last and the lowest modeling level. All information collected at the physical model design level is converted into the relational model. For this model, you specify data types, internal storage structures, table organizations, indexes, access paths, physical design parameters, and naming conventions for the database objects.
At this point, the target data management system and the model must correspond to a set of the system's FRs and NFRs, e.g., what kind of data will be queried from the database and how quickly it must be processed, respectively.

# OLTP vs OLAP Systems

## OLTP (Online Transaction Processing)
- **Definition:** A system for real-time transaction processing.  
- **Transaction:** A set of database operations executed as a single unit (all or none).  
- **Key Requirement:**  
  - Fast processing of simple queries from many users.  
  - Execution time: microseconds to milliseconds.  

## OLAP (Online Analytical Processing)
- **Definition:** A system designed for decision support and analysis, working with historical/archival data.  
- **Characteristics:**  
  - Complex queries involving many tables.  
  - Multidimensional schemas with aggregated historical data.  
  - Relatively low number of queries compared to OLTP.  

## Comparison of OLTP and OLAP

| Parameter                | OLAP Systems                                                                 | OLTP Systems                                              |
|--------------------------|------------------------------------------------------------------------------|-----------------------------------------------------------|
| **Data granularity**     | Detailed + aggregated data                                                    | Detailed data only                                        |
| **Storage format**       | Unified and consistent                                                       | Varies depending on tasks                                 |
| **Redundancy**           | Controlled redundancy                                                        | Maximum normalization, complex structures                 |
| **Data management**      | Periodic data addition                                                       | Insert, update, delete at any time                        |
| **Data volume**          | Includes all data, especially historical                                     | Operative (current) data only                             |
| **Query type**           | Ad-hoc, analytical, forecasting queries                                      | Predefined, simple transactional queries                  |

## Summary
- **OLTP:** Optimized for speed and concurrency in daily operations.  
- **OLAP:** Optimized for deep analysis, trend discovery, and decision-making using historical and aggregated data.  


# Data Warehouse (DWH) Architecture and Design Approaches

## Layers of DWH Architecture

- **Primary Data Layer (Raw/Staging):**  
  - Loads data from source systems in its original form.  
  - Preserves full history of changes.  
  - Abstracts upper layers from source formats, extraction methods, and device specifics.  

- **Core Data Layer:**  
  - Central integration layer that consolidates data from multiple sources.  
  - Standardizes structures and keys.  
  - Main point for data quality management and transformations.  
  - Shields consumers from complexity of source systems.  

- **Data Mart Layer:**  
  - Transforms data into subject-oriented structures for analysis.  
  - Used in BI dashboards and reporting tools.  
  - Focused slices of data for specific departments or user groups.  

---

## DWH Design Approaches

### Inmon Approach (Top-Down, Corporate DWH)
- **Process:**  
  - Start with full business analysis.  
  - Identify business areas, entities, attributes, and relationships.  
- **Result:** A centralized, enterprise-wide warehouse.  
- **Advantages:**  
  1. Single version of truth.  
  2. No contradictions in data.  
  3. Core layer reflects business processes.  
  4. Scales well with new sources.  
- **Disadvantages:**  
  1. Complex design, requires expert team.  
  2. Long initial implementation time.  

### Kimball Approach (Bottom-Up, Data Marts Collection)
- **Process:**  
  - Start with reporting needs.  
  - Analyze available sources.  
  - Design data marts for specific users.  
  - Transform raw data directly into marts.  
- **Result:** A set of data marts integrated into a DWH.  
- **Advantages:**  
  1. Quick results.  
  2. Incremental analysis of business areas.  
  3. Lower entry requirements for team skills.  
- **Disadvantages:**  
  1. Expensive maintenance with new sources.  
  2. Lack of standardized metrics across marts.  

# ACID Transactions

## Definition
A **transaction** is a sequence of commands that satisfies the ACID properties, ensuring database consistency when executed fully and without interference.

**ACID** = **Atomicity, Consistency, Isolation, Durability**

---

## Components
- **Atomicity:** A transaction is either fully completed or not executed at all.  
- **Consistency:** Each transaction moves the DB from one valid state to another.  
- **Isolation:** Concurrent transactions do not affect each other.  
- **Durability:** Data remains safe even after system failures.  

---

## Isolation Levels (SQL Standard)

| Level             | Prevented Anomalies                                                                 |
|-------------------|--------------------------------------------------------------------------------------|
| READ UNCOMMITTED  | Lost updates                                                                         |
| READ COMMITTED    | Lost updates, Dirty reads                                                            |
| REPEATABLE READ   | Lost updates, Dirty reads, Non-repeatable reads, Phantom reads                       |
| SERIALIZABLE      | Prevents all anomalies                                                               |

---

## Common Anomalies
- **Lost Update:** One transaction overwrites changes made by another.  
- **Dirty Read:** A transaction reads uncommitted changes of another.  
- **Non-Repeatable Read:** Re-reading the same row returns different results after another transaction updates it.  
- **Phantom Read:** Re-running a query returns new rows inserted by another transaction.  

# Data Lake, ETL/ELT, and Processing Architectures

## Data Lake
- **Definition:** A large-scale storage for raw, unstructured, semi-structured, and structured data collected by a company.  
- **Examples:** Video from drones, telemetry, photos, user logs, website metrics, system load indicators.  
- **Features:**  
  - Stores all data (useful or not).  
  - Flexible, supports multiple formats and sources.  
  - Requires extra processing for analytics.  
  - Cheaper to set up than DWH.  
- **Advantages:** Scalability, low cost (Hadoop-based), universality, fast experimentation.  
- **Risk:** *Data Swamp* — data collected but not used due to low quality or unclear value.  

---

## ETL vs ELT
- **ETL (Extract → Transform → Load):**  
  - Data extracted → transformed in staging area → loaded into DWH.  
  - Classic approach for structured data.  

- **ELT (Extract → Load → Transform):**  
  - Data extracted → immediately loaded into central repository → transformed inside storage.  
  - Common in modern cloud DWH.  

---

## Data Processing Types
- **Batch Processing:**  
  - Data processed in batches (e.g., daily, hourly).  
  - Efficient for OLAP; introduces delays; heavy peak loads.  
  - Typical for DWH (data often T−1).  

- **Stream Processing:**  
  - Continuous real-time processing of incoming data.  
  - Enables instant insights, but harder to develop/test.  
  - Less efficient for OLAP; smooth resource load.  

---

## Architectures
- **Lambda Architecture:**  
  - Combines batch layer (historical data, DWH) and real-time layer (stream views).  
  - Provides both accuracy and speed.  
  - Drawback: duplicated logic in both layers.  

- **Kappa Architecture:**  
  - Pure streaming-based architecture.  
  - Real-time processing with option to persist data in long-term storage.  
  - Simpler, avoids batch duplication.  

# Indexes & Partitions — Quick Cheatsheet

## 0) Mental model (why they exist)
- **No index, no partitions (“one big bag”)** → fastest writes, **slow reads** (full table scan).
- **Partitions (“many smaller bags”)** → prune irrelevant data ranges → **faster reads by key**, modest ops overhead.
- **Indexes (“catalogs”)** → jump straight to matching rows → **fast point/range lookups**, slower writes + extra storage.

---

## 1) Partitions (table-level sharding)
**What:** Split one large table into smaller pieces managed as one logical table.

**When to use**
- Clear split key (e.g., **date**, **region**, **business unit**).
- Very large tables (rule of thumb: millions+ rows). For small tables (< ~1M), benefits are minor.
- Archive/cold vs hot storage, faster maintenance (load, backup, drop old).

**Types (PostgreSQL examples but concepts are general)**
- **Range** (by date/number):
  ```sql
  CREATE TABLE sales (
    id serial, sale_date date, amount numeric
  ) PARTITION BY RANGE (sale_date);

Good for time-series.

    List (by discrete values):

CREATE TABLE employees (...) PARTITION BY LIST (department);

Good for categories (region, dept).

Hash (by hash(key)):

    CREATE TABLE sessions (...) PARTITION BY HASH (user_id);

    Good for even load distribution and parallelism.

Pros

    Pruning irrelevant partitions → faster queries.

    Easier data management (rolling windows, archiving).

    Better load/index maintenance (per-partition).

Cons

    More DDL/ops complexity.

    Queries without the partition key may touch many partitions.

    Hash partitions prune less effectively than range/list.

    Oracle: local vs global indexes (local = per partition; global = across table).
    PostgreSQL: effectively “local” by default.

2) Indexes (row access accelerators)

What: Separate structures to speed up searches/sorts/joins.

Use indexes for

    Primary/foreign keys (usually auto-indexed).

    Columns in WHERE, JOIN, ORDER BY, GROUP BY.

    High selectivity columns (many distinct values).

    Query patterns that return a small fraction of rows (≈ < 5% → index; > 5% → full scan often wins).

Avoid / be cautious

    Very frequent writes (each INSERT/UPDATE/DELETE maintains indexes).

    Low-selectivity columns (e.g., boolean, small enums) unless using a bitmap index (DW/OLAP).

    Huge tables with rare reads (index maintenance cost may outweigh benefit).

2.1 Logical types

    Clustered (table rows physically ordered by key; 1 per table):

        Fast ordered scans; slower writes (in-place reordering).

    Non-clustered (separate structure with pointers to rows):

        Multiple per table; extra storage; fast lookups.

    Unique vs Non-unique (enforce or not uniqueness).

    Simple (one column) vs Composite (multi-column; order matters like ORDER BY a,b).

2.2 Physical structures

    B-Tree / B+Tree (default ~90% of cases)

        Sorted by key, O(log n) search, great for point & range queries.

        Example:

        CREATE INDEX idx_number ON bag(number_cube);

        Reverse-key variants reduce hot spots for sequential inserts in clustered setups.

    Hash index

        Equality lookups col = ? only; direct bucket access; can shine on very large tables for equality filters.

        Collisions handled by chaining/recheck; range queries not supported.

    Bitmap index (DW/OLAP)

        Best for low-cardinality columns; super-fast AND/OR combinations.

        Higher storage; mostly used in analytical systems.

    GiST / GIN / SP-GiST (PostgreSQL)

        GiST: extensible tree for geometry, KNN, ranges.

        GIN: inverted index for arrays & full-text (token → posting list).

        SP-GiST: space-partitioned (tries, IP prefixes, etc.).

3) Putting it together (rules of thumb)

    Log tables / write-heavy → minimal indexes; maybe time-based range partitions.

    Time-series analytics → range partitions by date + B-Tree on query predicates.

    Lookup by ID/email → B-Tree index (simple or composite).

    Joins on foreign keys → indexes on join columns (both sides help).

    Boolean/small enums in DW → Bitmap index (not OLTP).

    If query returns > ~5% of table → consider full scan or partition pruning.

    For small tables → indexes help; partitions usually don’t.

4) Quick examples

Partitioned by color (list)

CREATE TABLE partitioned_bags (
  number_cube int,
  color text
) PARTITION BY LIST (color);

CREATE TABLE bags_red  PARTITION OF partitioned_bags FOR VALUES IN ('red');
CREATE TABLE bags_blue PARTITION OF partitioned_bags FOR VALUES IN ('blue');

Non-clustered index for fast lookup

CREATE TABLE indexed_bags (number_cube int);
CREATE INDEX idx_number ON indexed_bags (number_cube);

Clustered index idea (vendor-specific)
