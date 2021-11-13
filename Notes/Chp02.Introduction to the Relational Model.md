# Chapter 02: Introduction to the Relational Model

- Structure of Relational Databases
    
    > A relational database consists of a collection of tables(relations).
    > 
    
    > The relatively strict structure of relations results in several important practical advantages in the storage and processing of data.
    > 
    
    > That strict structure is suitable for well-defined and relatively static applications, but it is less suitable for applications where not only data but also the types and structure of those data change over time.
    > 
    
    > A modern enterprise needs to find a good balance between the efficiencies of structured data and those situations where a predetermined structure is limiting.
    > 
    - Table
        
        > It refers to a relation.
        > 
        
        > It has an unique name.
        > 
    - Relation
        
        > It refers to a table, an individual table in a relational database.
        > 
        
        > Is a set of tuples.
        > 
        
        > Corresponds to the programming-language notion of a variable.
        > 
    - Tuple
        
        > It refers to a record.
        > 
        
        > A tuple is simply a sequence (or list) of values.
        > 
        
        > A relationship between n values is represented mathematically by an n-tuple of values, that is, a tuple with n values, which corresponds to a row in a table.
        > 
    - Attribute
        
        > It refers to a column.
        > 
    - Relation instance
        
        > Refer to a specific instance of a relation, that is, containing a specific set of rows.
        > 
    - Domain
        
        > Is a set of permitted values, called the domain of that attribute.
        > 
        
        > We require the domains of all attributes of the relation be atomic.
        > 
    - Atomic domain
        
        > Elements of the domain are considered to be indivisible units.
        > 
    - Null value
        
        > Signifies that the value is unknown or does not exist.
        > 
        
        > Null values cause a number of difficulties when we access or update the database, and thus they should be eliminated if at all possible.
        > 
- Database Schema
    
    > The logical design of the database.
    > 
- Database Instance
    
    > A snapshot of the data in the database at a given instant in time.
    > 
- Relation Schema
    
    > Corresponds to the programming- language notion of type definition.
    > 
    
    > It consists of a list of attributes and their corresponding domains.
    > 
    
    > Using common attributes in relation schemas is one way of relating tuples of distinct relations.
    > 
- Relation Instance
    
    > Corresponds to the programming-language no- tion of a value of a variable.
    > 
    
    > The value of a given variable may change with time; simi- larly the contents of a relation instance may change with time as the relation is updated.
    > 
    
    > In contrast, the schema of a relation does not generally change.
    > 
- Keys
    
    > Specify how tuples within a given relation are distinguished.
    > 
    
    > No two tuples in a relation are allowed to have exactly the same value for all attributes.
    > 
    
    > Any two individual tuples in the relation are prohibited from having the same value on the key attributes at the same time.
    > 
    - Super key
        
        > Is a set of one or more attributes that, taken collectively, allow us to identify uniquely a tuple in the relation.
        > 
        
        > A superkey may contain extraneous attributes.
        > 
    - Candidate key
        
        > Refers to minimal superkeys.
        > 
        
        > It is possible that several distinct sets of attributes could serve as a candidate key.
        > 
        
        > None of the attributes of the set that forms the candidate be a candidate key on its own.
        > 
    - Primary key
        
        > Denotes a candidate key that is chosen by the database designer as the principal means of identifying tuples within a relation.
        > 
        
        > It is customary to list the primary key attributes of a relation schema before the other attributes.
        > 
        
        > Underlined to indicate it is a primary key.
        > 
        
        > Primary keys must be chosen with care.
        > 
        
        > The primary key should be chosen such that its attribute values are never, or are very rarely, changed.
        > 
    - Primary key constraints
        
        > The designation of a key represents a constraint in the real-world enterprise being modeled.
        > 
    - Foreign key
        
        > Is a field (or collection of fields) in one table, that refers to the Primary Key in another table.
        > 
        
        > It appears as an arrow in schema diagram.
        > 
    - Foreign key constraints
        
        > A referential-integrity con- straint, relaxes the requirement that the referenced attributes form the primary key of the referenced relation.
        > 
        
        > Enforce referential integrity constraint, which essentially says that if column value A refers to column value B, then column value B must exist.
        > 
        - Referencing relation
            
            > The relation that contains the foreign key constraint.
            > 
        - Referenced relation
            
            > The relation that contains the primary key that the foreign key refers to.
            > 
        - Referential integrity constraint
            
            > Requires that the values appearing in specified attributes of any tuple in the referencing relation also appear in specified attributes of at least one tuple in the referenced relation.
            > 
- Schema Diagram
    
    > A schema diagram is a diagram which contains entities and the attributes that will define that schema, like Entity-Relationship-Diagram.
    > 
- Query Language Types
    
    > A query language is a language in which a user requests information from the database.
    > 
    - Imperative
        
        > User instructs the system to perform a specific sequence of operations on the database to compute the desired result.
        > 
    - Functional
        
        > The computation is expressed as the evaluation of functions that may operate on data in the database or on the results of other functions.
        > 
        
        > Functions are side-effect free, and they do not update the program state.
        > 
    - Declarative
        
        > SQL is based on Declarative Paradigm.
        > 
        
        > User describes the desired information without giving a specific sequence of steps or function calls for obtaining that information.
        > 
        
        > The desired information is typically described using some form of mathematical logic. It is the job of the database system to figure out how to obtain the desired information.
        > 
- Relational algebra
    
    > Consists of a set of operations that take one or two relations as input and produce a new relation as their result.
    > 
- Relational-algebra operations
    
    > There are unary and binary operations.
    > 
    
    > Database systems do not allow users to write queries in relational algebra.
    > 
    
    > Tables in database systems are permitted to contain duplicates unless a specific constraint prohibits it.
    > 
    - Select σ
        
        > Selects tuples that satisfy a given predicate.
        > 
        
        > The predicate appears as a subscript to σ.
        > 
        
        > The argument relation is in parentheses after the σ.
        > 
    - Project Π
        
        > Returns its argument relation, with certain attributes left out.
        > 
        
        > The basic version of the project operator ΠL(E) allows only attribute names to be present in the list L.
        > 
        
        > A generalized version of the operator allows expressions involving attributes to appear in the list L.
        > 
    - Cartesian product ×
        
        > Allows us to combine information from any two relations.
        > 
        
        > The resultant relation contains AxB records, where A and B are the number or records in relation1 and relation2.
        > 
    - Join ⋈
        
        > Allows us to combine a selection and a Cartesian product into a single operation.
        > 
    - Set operations
        
        > Inputs from both relations must have the same number of attributes(arity).
        > 
        
        > The type of the i-th attribute from both relations must have the type.
        > 
        - Union ∪
            
            > It includes all tuples that that appear in either or both of the two relations.
            > 
        - Set diﬀerence −
            
            > It includes all tuples that are in A but not in B.
            > 
        - Set intersection ∩
            
            > Allows us to find tuples that are in both the input relations.
            > 
    - Assignment←
        
        > Assign a relational-algebra expression a to temporary relation variable.
        > 
        
        > A query can be written as a sequential program consisting of a series of assignments followed by an expression.
        > 
        
        > Assignment must always be made to a temporary relation variable.
        > 
        
        > Assignments to permanent relations constitute a database modification.
        > 
    - Rename ρ
        
        > It gives a name to a relational-algebra expression.
        > 
    - Equivalent Queries
        
        > There is often more than one way to write a query in relational algebra.
        > 
        
        > Query optimizers in database systems typically look at what result an expression computes and find an efficient way of computing that result, rather than following the exact sequence of steps specified in the query. The algebraic structure of relational algebra makes it easy to find efficient but equivalent alternative expressions.
        >