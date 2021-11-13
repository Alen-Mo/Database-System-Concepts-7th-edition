# Chapter 01: Introduction

- Database-Management System ( DBMS )
    
    > A collection of interrelated data and a set of programs to access those data.
    > 
    
    > A major purpose of a database system is to
    provide users with an abstract view of the data.
    > 
- Database-System Applications
    
    > Highly valuable.
    > 
    
    > Relatively large.
    > 
    
    > Accessed by multiple users and applications, often at the same time.
    > 
- File-Processing System
    - Data Redundancy and Inconsistency
        
        > The same information may be duplicated in several places (files). This redundancy leads to higher storage and access cost. In addition, it may lead to data inconsistency; that is, the various copies of the same data may no longer agree.
        > 
    - Diﬃculty in Accessing Data
        
        > There is no application program on hand to meet the requirements.
        > 
        
        > The point here is that conventional file-processing environments do not allow needed data to be retrieved in a convenient and efficient manner. More responsive data-retrieval systems are required for general use.
        > 
    - Data Isolation
        
        > Because data are scattered in various files, and files may be in different formats, writing new application programs to retrieve the appropriate data is difficult.
        > 
    - Integrity Problems & Consistency Constraints
        
        > The data values stored in the database must satisfy certain types of consistency constraints.
        > 
    - Atomicity Problems
        
        > Atomicity — all-or-none.
        > 
        
        > If a failure occurs, the data be restored to the consistent state that existed prior to the failure.
        > 
        
        > Atomic — it must happen in its entirety or not at all.
        > 
        
        > It is difficult to ensure atomicity in a conventional file-processing system.
        > 
    - Concurrent-Access Anomalies
        
        > Interaction of concur-rent updates is possible and may result in inconsistent data.
        > 
        
        > To guard against this possibility, the system must maintain some form of supervision. But supervision is difficult to provide because data may be accessed by many different application programs that have not been coordinated previously.
        > 
    - Security Problems
        
        > Not every user of the database system should be able to access all the data.
        > 
        
        > But since application programs are added to
        the file-processing system in an ad hoc manner, enforcing such security constraints is difficult.
        > 
- View of Data
    - Data Models
        
        > A collection of conceptual tools for describing data, data relationships, data semantics, and consistency constraints.
        > 
        - Relational Model
            
            > a collection of tables to represent both data and the relationships among those data. Each table has multiple columns, and each column has a unique name.
            > 
            
            > tables are also known as relations.
            > 
            
            > a record-based model.
            > 
        - Entity-Relationship Model
            
            > a collection of basic objects, called entities, and relationships among these objects.
            > 
            
            > an entity is a “thing” or “object” in the real world that is distinguishable from other objects.
            > 
        - Semi-structured Data Model
            
            > permits the specification of data where individual data items of the same type may have different sets of attributes.
            > 
            
            > JSON & XML are examples of Semi-structured Data.
            > 
        - Object-Based Data Model
            
            > this can be seen as extending the relational model with notions of encapsulation, methods, and object
            identity.
            > 
    - Data Abstraction
        
        > Since many database-system users are not computer trained, developers hide the complexity from users through several levels of data abstraction, to simplify users’ interactions with the system.
        > 
        - Physical level
            
            > describes how the data are actually stored. The physical level describes complex low-level data structures in detail.
            > 
            
            > record could be described as a block of consecutive bytes.
            > 
        - Logical level
            
            > describes what data are stored in the database, and what relationships exist among those data.
            > 
            
            > the logical level thus describes the entire database in terms of a small number of relatively simple structures.
            > 
            
            > although implementation of the simple structures at the logical level may involve complex physical-level structures, the user of the logical level does not
            need to be aware of this complexity. This is referred to as physical data independence.
            > 
            
            > record could be described as a type definition.
            > 
        - View level
            
            > describes only part of the entire database.
            > 
            
            > the system may provide many views for the same database.
            > 
    - Instances and Schemas
        
        > Instance is the collection of information stored in the database at a particular moment.
        > 
        
        > Schema is the overall design of the database.
        > 
        
        > Database schema corresponds to the variable declarations (along with associated type definitions) in a program.
        > 
        
        > The values of the variables in a program at a point
        in time correspond to an instance of a database schema.
        > 
        
        > Database systems have several schemas, partitioned according to the levels of abstraction.
        > 
        - physical schema
            
            > Describes the database design at the physical level.
            > 
            
            > The physical schema is hidden beneath the logical schema.
            > 
        - logical schema
            
            > Describes the database design at the logical level.
            > 
            
            > The logical schema is by far the most important in terms of its effect on application programs, since programmers construct applications by using the logical schema.
            > 
        - subschemas
            
            > Describes different views of the database.
            > 
- Database Languages
    
    > The data-definition and data-manipulation languages are not two separate languages; instead they simply form parts of a single database language, such as the SQL language.
    > 
    - Data-Definition Language
        
        > To specify the database schema.
        > 
        
        > Allows one to define tables with data types and integrity
        constraints.
        > 
        
        > Also used to specify additional properties of the data.
        > 
        
        > Specify the storage structure and access methods used by the database system by a set of statements in a special type of DDL called a data storage and definition
        language.
        > 
        - Domain Constraints
            
            > A domain of possible values must be associated with every attribute (for example, integer types, character types, date/time types).
            > 
            
            > Domain constraints are the most elementary form of integrity constraint.
            > 
            
            > Tested easily by the system whenever a new data item is entered into the database.
            > 
        - Referential Integrity
            
            > To ensure that a value that appears in one relation for a given set of attributes also appears in a certain set
            of attributes in another relation (referential integrity).
            > 
            
            > Database modifications can cause violations of referential integrity.
            > 
            
            > When a referential-integrity constraint is violated, the normal procedure is to reject the action that caused the violation.
            > 
        - Authorization
            
            > We may want to differentiate among the users as far as the type of access they are permitted on various data values in the database.
            > 
            
            > We may assign the user all, none, or a
            combination of these types of authorization.
            > 
            - read authorization
                
                > Allows reading, but not modification, of data.
                > 
            - insert authorization
                
                > Allows insertion of new data, but not modification of existing data.
                > 
            - update authorization
                
                > Allows modification, but not deletion, of data.
                > 
            - delete authorization
                
                > Allows deletion of data
                > 
        - data dictionary & metadata
            
            > The database system consults the data dictionary before reading or modifying actual data.
            > 
            
            > The output of the DDL is placed in the data dictionary, which contains metadata — that is, data about data.
            > 
            
            > Data dictionary is considered to be a special type of table that can be accessed and updated only by the database system itself (not a regular user).
            > 
    - Data-Manipulation Language
        
        > To express database queries and updates.
        > 
        
        > Enables users to access or manipulate data as organized by the appropriate data model.
        > 
        
        > Types of access are: Retrieval, Insertion, Deletion, Modification.
        > 
        
        > At the physical level, we must define algorithms that allow efficient access to data.
        > 
        - Procedural DML
            
            > Require a user to specify what data are needed and how to get those data.
            > 
        - Declarative DML(non-procedural DML)
            
            > Require a user to specify what data are needed without specifying how to get those data.
            > 
            
            > Declarative DML s are usually easier to learn and use than procedural DMLs. However, since a user does not have to specify how to get the data, the database system has to figure out an efficient means of accessing data.
            > 
        - query & query language
            
            > Query is a statement requesting the retrieval of information.
            > 
            
            > A query takes as input several tables (possibly only one) and always returns a single table.
            > 
            
            > The query processor component of the database system translates DML queries into sequences of actions at the physical level of the database system.
            > 
    - Database Access from Application Programs Interface(API)
        
        > DML statements need to be sent from the host to the
        database where they will be executed. This is most commonly done by using an application-program interface (set of procedures) that can be used to send DML and DDL statements to the database and retrieve the results.
        > 
- Database Design
    
    > Database design mainly involves the design of the database schema.
    > 
    
    > A high-level data model provides the database designer with a conceptual frame-work in which to specify the data requirements of the database users and how the database will be structured to fulfill these requirements.
    > 
    
    > The initial phase of database design, then, is to characterize fully the data needs of the prospective database users. The database designer needs to interact extensively with domain experts and users to carry out this task. The outcome of this phase is a specification of user requirements.
    > 
    
    > Next, the designer chooses a data model, and by applying the concepts of the chosen data model, translates these requirements into a conceptual schema of the database. The schema developed at this conceptual-design phase provides a detailed overview of the enterprise. The designer reviews the schema to confirm that all data requirements are indeed satisfied and are not in conflict with one another. The designer can also examine the design to remove any redundant features. The focus at this point is on describing the data and their relationships, rather than on specifying physical storage details.
    > 
    - Conceptual Design(Abstract Model)
        
        > In terms of the relational model, the conceptual-design process involves decisions on what attributes we want to capture in the database and how to group these attributes to form the various tables.
        > 
        
        > The “what” part is basically a business decision.
        > 
        
        > The “how” part is mainly a computer-science problem.
        > 
        
        > There are principally two ways to tackle the problem. The first one is to use the entity-relationship model, the other is to employ a set of algorithms as normalization.
        > 
        
        > A fully developed conceptual schema indicates the functional requirements of the enterprise.
        > 
        
        > In a specification of functional requirements, users describe the kinds of operations (or transactions) that will be performed on the data. Example operations include
        modifying or updating data, searching for and retrieving specific data, and deleting data. At this stage of conceptual design, the designer can review the schema to ensure it meets functional requirements.
        > 
        
        > The process of moving from an abstract data model to the implementation of the database proceeds in two final design phases which are Logical design phase and Physical design phase.
        > 
    - Logical Design
        
        > The designer maps the high-level conceptual schema onto the implementation data model of the database system that will be used.
        > 
        
        > The designer uses the resulting system-specific database schema in the subsequent Physical design phase.
        > 
    - Physical Design
        
        > In which the physical features of the database are specified. These features include the form of file organization and the internal storage structures.
        > 
- Database Engine
    
    > The functional components of a database system can be broadly divided into the storage manager, the query processor components, and the transaction management component.
    > 
    - Storage manager Components
        
        > The storage manager translates the various DML statements into low-level file-system commands. Thus, the storage manager is responsible for storing, retrieving, and updating data in the database.
        > 
        
        > Is important because databases typically require a large amount of storage space.
        > 
        
        > Provides the interface between the low-level data stored in the database and the application programs and queries submitted to the system.
        > 
        
        > The storage manager is responsible for the interaction with the file manager. The raw data are stored on the disk using the file system provided by the operating system.
        > 
        
        > The storage manager implements several data structures as part of the physical
        system implementation which are Data files, Data dictionary, Indices.
        > 
        - Authorization and integrity manager
            
            > Tests for the satisfaction of integrity constraints and checks the authority of users to access data.
            > 
        - Transaction manager
            
            > Ensures that the database remains in a consistent (correct) state despite system failures, and that concurrent transaction executions proceed without conflicts.
            > 
        - File manager
            
            > Manages the allocation of space on disk storage and the data structures used to represent information stored on disk.
            > 
        - Buﬀer manager
            
            > Is responsible for fetching data from disk storage into main memory, and deciding what data to cache in main memory, it also enables the database to handle data sizes that are much larger than the size of main memory.
            > 
        - Data ﬁles
            
            > Store the database itself.
            > 
        - Data dictionary
            
            > Which stores metadata about the structure of the database which is the schema of the database.
            > 
        - Indices
            
            > Provide fast access to data item
            > 
    - Query Processor Components
        
        > Is important because it helps the database system to simplify and facilitate access to data.
        > 
        
        > The query processor allows database users to obtain good performance while being able to work at the view level and not be burdened with understanding the physical-level details of the implementation of the system.
        > 
        
        > It is the job of the database system to translate updates and queries written in a non-procedural language, at the logical level, into an efficient sequence of operations at the physical level.
        > 
        - DDL interpreter
            
            > Interprets DDL statements and records the definitions in the data dictionary.
            > 
        - DML compiler
            
            > Translates DML statements into an evaluation plan consisting of low-level instructions that the query-evaluation engine understands.
            > 
        - Query optimizer
            
            > A query can usually be translated into any of a number of alternative evaluation plans that all give the same result.
            > 
            
            > The DML compiler also performs query optimization; that is, it picks the lowest cost evaluation plan from among the alternatives.
            > 
        - Query evaluation engine
            
            > Executes low-level instructions generated by the DML compiler.
            > 
    - Transaction Manager Components
        
        > A transaction is a collection of operations that performs a single logical function in a database application.
        > 
        
        > Each transaction is a unit of both atomicity and consistency.
        > 
        
        > If the database was consistent when a transaction started, the database must
        be consistent when the transaction successfully terminates. However, during the execution of a transaction, it may be necessary temporarily to allow inconsistency.
        > 
        
        > If the transaction contains many separate programs, each program by itself doesn't transform the database from a consistent state to a new consistent state, those programs aren't transactions.
        > 
        
        > Is important because it allows application developers to treat a sequence of database accesses as if they were a single unit that either happens in its entirety or not at all(Atomicity).
        > 
        
        > This permits application developers to think at a higher level of abstraction about the application without needing to be concerned with the lower-level details of managing the effects of concurrent access to the data and of system failures.
        > 
        
        > Today parallel processing is key for handling very large amounts of data efficiently. Modern database engines pay a lot of attention to parallel data storage and parallel query processing.
        > 
        
        > Transaction manager consists of the concurrency-control manager and the recovery
        manager.
        > 
        - Recovery manager(Atomicity + Durability)
            
            > Ensuring the atomicity and durability properties.
            > 
            
            > To ensure the atomicity property, a failed transaction must have no effect on the state of the database. Thus, the database must be restored to the state in which it was before the transaction in question started executing. The database system must therefore perform failure recovery.
            > 
            - Failure recovery
                
                > Detecting system failures and restore the database to the state that existed prior to the occurrence of the failure.
                > 
            - Atomicity
                
                > Ensuring the atomicity property.
                > 
        - Concurrency-control manager
            
            > To control the interaction among the concurrent transactions, to ensure the consistency of the database.
            > 
            - Consistency
                
                > Correctness Requirement.
                > 
                
                > States that only valid data will be written to the database.
                > 
        - Durability
            
            > Persistence Requirement.
            > 
            
            > Ensures transactions are saved permanently and do not accidentally disappear or get erased, even during a database crash.
            > 
- Database and Application Architecture
    - Two-Tier Architecture
        
        > Where the application resides at the client machine, and invokes database system functionality at the server machine through query language statements.
        > 
    - Three-Tier Architecture
        
        > Where the client machine acts as merely a front end and does not contain any direct database calls.
        > 
        
        > The front end communicates with an application server.
        > 
        
        > The application server, in turn, communicates with a database system to access data.
        > 
        
        > The application server, in turn, communicates with a database system to access data.
        > 
        
        > The business logic of the application, which says what actions to carry out under what conditions, is embedded in the application server, instead of being distributed across multiple clients.
        > 
        
        > Three-tier applications provide better security as well as better performance than two-tier applications.
        > 
- Database Users and Administrators
    - Database Users and User Interfaces
        - Naı̈ve users
            
            > Interact with the system by using predefined user interfaces, such as web or mobile applications.
            > 
        - Application programmers
            
            > Are computer professionals who write application programs. Application programmers can choose from many tools to develop user interfaces.
            > 
        - Sophisticated users
            
            > Interact with the system without writing programs. Instead, they form their requests either using a database query language or by using tools such as data analysis software. Analysts who submit queries to explore data in the database fall in this category.
            > 
    - Database Administrator
        - Schema deﬁnition
            
            > The DBA creates the original database schema by executing a set of data definition statements in the DDL.
            > 
        - Schema and physical-organization modification
            
            > The DBA carries out changes to the schema and physical organization to reflect the changing needs of the organization, or to alter the physical organization to improve performance.
            > 
        - Granting of authorization for data access
            
            > By granting different types of authorization, the database administrator can regulate which parts of the database various users can access. The authorization information is kept in a special system structure that the database system consults whenever a user tries to access the data in the system.
            > 
        - Routine maintenance
            
            > Periodically backing up the database onto remote servers, to prevent loss of
            data in case of disasters such as flooding.
            > 
            
            > Ensuring that enough free disk space is available for normal operations, and
            upgrading disk space as required.
            > 
            
            > Monitoring jobs running on the database and ensuring that performance is not
            degraded by very expensive tasks submitted by some users.
            >