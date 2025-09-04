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


