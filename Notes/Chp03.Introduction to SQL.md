# Chapter 03: Introduction to SQL

- Overview of the SQL Query Language
    
    > Database systems typically translate SQL queries into a lower-level representation based on relational algebra, and they perform query optimization and query evaluation using this representation.
    > 
    - Data-deﬁnition language(DDL)
        
        > For defining relation schemas, deleting relations, and modifying relation schemas.
        > 
    - Data-manipulation language(DML)
        
        > To insert tuples into, delete tuples from, and modify tuples in the database.
        > 
    - Integrity
        
        > SQL DDL includes commands for specifying integrity constraints that the data stored in the database must satisfy.
        > 
        
        > Updates that violate integrity constraints are disallowed.
        > 
    - View Definition
        
        > SQL DDL includes commands for defining views.
        > 
    - Transaction control
        
        > SQL includes commands for specifying the beginning and end points of transactions.
        > 
    - Embedded SQL and Dynamic SQL
        
        > Define how SQL statements can be embedded within general-purpose programming languages, such as C, C++, and Java.
        > 
    - Authorization
        
        > SQL DDL includes commands for specifying access rights to relations and views.
        > 
- SQL Data Definition
    
    > DDL allows specification about each relation, including:
    > 
    
    > The schema for each relation.
    > 
    
    > The types of values associated with each attribute.
    > 
    
    > The integrity constraints.
    > 
    
    > The security and authorization information for each relation.
    > 
    
    > The physical storage structure of each relation on disk.
    > 
    - SQL basic types
        - char(n)
            
            > A fixed-length character string with user-specified length n. The full form, character, can be used instead.
            > 
        - varchar(n)
            
            > A variable-length character string with user specified maximum length n. The full form, character varying, is equivalent.
            > 
            
            > SQL provides nvarchar type to store multilingual data using the Unicode representation.
            > 
        - int
            
            > An integer (a finite subset of the integers that is machine dependent). The full form, integer, is equivalent.
            > 
        - smallint
            
            > A small integer (a machine-dependent subset of the integer type).
            > 
        - numeric(p, d)
            
            > A fixed-point number with user-specified precision. The number consists of p digits (plus a sign), and d of the p digits are to the right of the decimal point.
            > 
        - real, double precision
            
            > Floating-point and double-precision floating-point numbers with machine-dependent precision.
            > 
        - float(n)
            
            > A floating-point number with precision of at least n digits.
            > 
        - null
            
            > Each type may include a special value called the null value.
            > 
            
            > A null value indicates an absent value that may exist but be unknown or that may not exist at all.
            > 
    - Basic Schema Definition
        
        > We define an SQL relation by using the create table command.
        > 
        
        > We can add the specifications like: Domain of attribute, Primary Key, Foreign Key, Not Null.
        > 
        
        > If you are making an update that violates the integrity constraints, SQL flags an error and prevents the update.
        > 
        
        > To remove a relation, use the drop table command, it deletes all information about the dropped relation from the database.
        > 
        
        > To add attributes to an existing relation, use the alter table command, all tuples in the relation are assigned null as the value for the new attribute.
        > 
- Basic Structure of SQL Queries
    
    > Consists of three clauses: select, from, and where.
    > 
    
    > A query takes as its input the relations listed in the from clause, operates on them as specified in the where and select clauses, and then produces a relation as the result.
    > 
    
    > Select: is used to list the attributes desired in the result of a query.
    > 
    
    > From: is a list of the relations to be accessed in the evaluation of the query.
    > 
    
    > Where: is a predicate involving attributes of the relation in the from clause.
    > 
    
    > If the where clause is omitted, the predicate P is true.
    > 
    
    > Clauses in operational order: first from, then where, and then select.
    > 
    
    > The from clause by itself defines a Cartesian product of the relations listed in the clause.
    > 
    
    > The from clause could be understood as an iterative process that generates tuples for the result relation of the from clause.
    > 
    
    > The result relation has all attributes from all the relations in the from clause.
    > 
    
    > The Cartesian product by itself combines tuples from relations associated to it.
    > 
    
    > If you omitted the where clause from a query on two relations, the result will equal the Cartesian product of these two relations.
    > 
    - Queries on a Single Relation
        
        > Queries access the data from a single relation.
        > 
    - Queries on a Multiple Relations
        
        > Queries access the data from multiple relations.
        > 
- Additional Basic Operations
    - Rename Operation
        
        > SQL provides a way of renaming the attributes of a result relation. It uses the as clause.
        > 
        
        > The as clause can appear in both the select and from clauses.
        > 
        
        > One reason to rename a relation is to replace a long relation name with a shortened version that is more
        convenient to use elsewhere in the query.
        > 
        
        > Another reason to rename a relation is a case where we wish to compare tuples in the same relation and without renaming, it becomes impossible to distinguish one tuple from the other.
        > 
        - Correlation Name
            
            > An identifier that is used to rename a relation.
            > 
            
            > A *correlation name* can be defined in the FROM clause of a query and in the first clause of an UPDATE or DELETE statement.
            > 
            
            > It is also commonly referred to as a table alias, or a correlation variable, or a tuple variable.
            > 
    - String Operations
        
        > SQL specifies strings by enclosing them in single quotes.
        > 
        
        > A single quote character that is part of a string can be specified by using two single quote characters.
        > 
        
        > The SQL standard specifies that the equality operation on strings is case sensitive. This default behavior can, however, be changed, either at the database level or at the level of specific attributes.
        > 
        
        > Some SQL functions on character strings, such as concatenating (using “∥”), extracting substrings, finding the length of strings, converting strings to uppercase (using the function upper(s) where s is a string) and lowercase (using the function lower(s)), removing spaces at the end of the string (using trim(s)), and so on.
        > 
        
        > Pattern matching can be performed on strings using the operator like. Patterns are case sensitive.
        > 
        
        > Percent (%): The % character matches any substring.
        > 
        
        > Underscore (_): The _ character matches any character.
        > 
        
        > The escape character is used immediately before a special pattern character to indicate that the special pattern character is to be treated like a normal character.
        > 
        
        > SQL allows us to search for mismatches instead of matches by using the not like comparison operator.
        > 
    - Attribute Specification in the Select Clause
        
        > The asterisk symbol “ * ” can be used in the select clause to denote “all attributes.”
        > 
        
        > A select clause of the form select * indicates that all attributes of the result relation of the from clause are selected.
        > 
    - Ordering the Display of Tuples
        
        > SQL offers the user some control over the order in which tuples in a relation are displayed.
        > 
        
        > The order by clause causes the tuples in the result of a query to appear in sorted order.
        > 
        
        > By default, the order by clause lists items in ascending order, we may specify desc for descending order or asc for ascending order.
        > 
        
        > Ordering can be performed on multiple attributes.
        > 
    - Where-Clause Predicates
        
        > SQL includes a between comparison operator to simplify where clauses that specify that a value be less than or equal to some value and greater than or equal to some other value, Similarly, we can use the not between comparison operator.
        > 
        
        > The comparison operators can be used on tuples, and the ordering is defined lexicographically, like (a1, a2) <= (b1, b2) is true if a1 <= b1 and a2 <= b2.
        > 
- Set Operations
    
    > The SQL operations union, intersect, and except operate on relations and correspond to the mathematical set operations ∪, ∩, and −.
    > 
    - Union Operation
        
        > It includes all tuples that that appear in either or both of the two relations.
        > 
        
        > The union operation automatically eliminates duplicates, unlike the select clause.
        > 
        
        > If we want to retain all duplicates, we must write union all in place of union.
        > 
    - Intersect Operation
        
        > Allows us to find tuples that are in both the input relations.
        > 
        
        > The intersect operation automatically eliminates duplicates.
        > 
        
        > If we want to retain all duplicates, we must write intersect all in place of intersect.
        > 
    - Except Operation
        
        > It includes all tuples that are in A but not in B.
        > 
        
        > The operation automatically eliminates duplicates in the inputs before performing set difference.
        > 
        
        > If we want to retain duplicates, we must write except all in place of except.
        > 
- Null Values
    
    > Null values present special problems in relational operations, including arithmetic operations, comparison operations, and set operations.
    > 
    
    > The result of an arithmetic expression (involving, for example, +, −, ∗, or ∕) is null if any of the input values is null.
    > 
    
    > SQL therefore treats as unknown the result of any comparison involving a null value (other than predicates is null and is not null, which are described later in this section). This creates a third logical value in addition to true and false.
    > 
    
    > The definitions of the Boolean operations are extended to deal with the value unknown.
    > 
    
    > And: The result of true and unknown is unknown, false and unknown is false, while unknown and unknown is unknown.
    > 
    
    > Or: The result of true or unknown is true, false or unknown is unknown, while unknown or unknown is unknown.
    > 
    
    > Not: The result of not unknown is unknown.
    > 
    
    > If the where clause predicate evaluates to either false or unknown for a tuple, that tuple is not added to the result.
    > 
    
    > The predicate is not null succeeds if the value on which it is applied is not null.
    > 
    
    > SQL allows us to test whether the result of a comparison is unknown, rather than true or false, by using the clauses is unknown and is not unknown.
    > 
    
    > Even if some of the attributes have a null value. Using the distinct clause then retains only one copy of such identical tuples.
    > 
    
    > The approach of treating tuples as identical if they have the same values for all attributes, even if some of the values are null, is also used for the set operations union, intersection, and except.
    > 
- Aggregate Functions
    
    > Aggregate functions are functions that take a collection (a set or multiset) of values as input and return a single value.
    > 
    
    > The input to sum and avg must be a collection of numbers, but the other operators can operate on collections of non-numeric data types, such as strings, as well.
    > 
    - Basic Aggregation
        
        > If we do want to eliminate duplicates, we use the keyword distinct in the aggregate expression.
        > 
        - COUNT
            
            > It counts how many rows are in a particular column.
            > 
        - SUM
            
            > It adds together all the values in a particular column.
            > 
        - MIN and MAX
            
            > They return the lowest and highest values in a particular column, respectively.
            > 
        - AVG
            
            > It calculates the average of a group of selected values.
            > 
            
            > Retaining duplicates is important in computing an average.
            > 
    - Aggregation with Grouping
        
        > To a group of sets of tuples; we specify this in SQL
        using the group by clause.
        > 
        
        > The attribute or attributes given in the group by clause are used to form groups.
        > 
        
        > Tuples with the same value on all attributes in the group by clause are placed in one group.
        > 
        
        > The group by clause has been omitted, so the entire relation is treated as a single group.
        > 
        
        > When an SQL query uses grouping, it is important to ensure that the only attributes that appear in the select statement without being aggregated are those that are present in the group by clause. In other words, any attribute that is not present in the group by clause may appear in the select clause only as an argument to an aggregate function, otherwise the query is treated as erroneous.
        > 
    - The Having Clause
        
        > To apply conditions on groups rather than on tuples.
        > 
        
        > The condition does not apply to a single tuple; rather, it applies to each group constructed by the group by clause.
        > 
        
        > SQL applies predicates in the having clause after groups have been formed, so aggregate functions may be used in the having clause.
        > 
        
        > As was the case for the select clause, any attribute that is present in the having clause without being aggregated must appear in the group by clause, otherwise the query is erroneous.
        > 
    - Aggregation with Null and Boolean Values
        
        > Null values, when they exist, complicate the processing of aggregate operators.
        > 
        
        > The SQL standard says that the sum operator should ignore null values in its input.
        > 
        
        > All aggregate functions except count (*) ignore null values in their input collection.
        > 
        
        > The aggregate functions some and every can be applied on a collection of Boolean values, and compute the disjunction (or) and conjunction (and), respectively,
        of the values.
        > 
- Nested Subqueries
    
    > A subquery is a select-from-where expression that is nested within another query.
    > 
    
    > A common use of subqueries is to perform tests for set membership, make set comparisons, and determine set cardinality by nesting subqueries in the where clause.
    > 
    - Set Membership
        
        > SQL allows testing tuples for membership in a relation.
        > 
        
        > The in connective tests for set membership, where the set is a collection of values produced by a select clause. The not in connective tests for the absence of set membership.
        > 
        
        > If we want to get intersection between two sets, we used to use the Intersect Operation (∩), you can alternatively do that using subqueries by checking for membership, but you also need to use distinct keyword because it is not the default as the Intersect Operation (∩).
        > 
        
        > We can form the Intersect Operation (∩) by using in keyword with subqueries, the Except Operation (−) by using not in with keyword subqueries.
        > 
        
        > The in and not in operators can also be used on enumerated sets.
        > 
        
        > It is also possible to test for membership in an arbitrary relation(more than one attribute) in SQL.
        > 
    - Set Comparison
        
        > As an example of the ability of a nested subquery to compare sets.
        > 
        
        > The > some is equal to “greater than at least one”, so we can use it with the result set produced from the subquery.
        > 
        
        > SQL also allows < some, <= some, >= some, = some, and <> some comparisons.
        > 
        
        > You can find out that = some is identical to in, whereas <> some is not the same as not in.
        > 
        
        > SQL also allows < all, <= all, >= all, = all, and <> all comparisons.
        > 
        
        > You can find out that <> all is identical to not in, whereas = all is not the same as in.
        > 
    - Test for Empty Relations
        
        > SQL includes a feature for testing whether a subquery has any tuples in its result.
        > 
        
        > The exists construct returns the value true if the argument subquery is nonempty.
        > 
        
        > We can test for the nonexistence of tuples in a subquery by using the not exists construct.
        > 
        
        > The correlation name from an outer query, can be used in a subquery in the where clause.
        > 
        
        > A subquery that uses a correlation name from an outer query is called a correlated subquery.
        > 
    - Test for the Absence of Duplicate Tuples
        
        > SQL includes a Boolean function for testing whether a subquery has duplicate tuples in its result.
        > 
        
        > The unique construct returns the value true if the argument subquery contains no duplicate tuples.
        > 
        
        > We can test for the existence of duplicate tuples in a subquery by using the not unique construct.
        > 
    - Subqueries in the From Clause
        
        > SQL allows a subquery expression to be used in the from clause.
        > 
        
        > The key concept applied here is that any select-from where expression returns a relation as a result and, therefore, can be inserted into another select-from where anywhere that a relation can appear.
        > 
        
        > The subquery in the from clause will generate a relation which would be the input relation we access to get data from.
        > 
        
        > We note that nested subqueries in the from clause cannot use correlation variables from other relations in the same from clause. However, SQL:2003 , allows a subquery in the from clause that is prefixed by the lateral keyword to access attributes of preceding tables or subqueries in the same from clause. Without the lateral clause, the subquery cannot access the correlation variable from the outer query.
        > 
    - The With Clause
        
        > The with clause provides a way of defining a temporary relation whose definition is available only to the query in which the with clause occurs.
        > 
        
        > The produced relation is available for use only within
        later parts of the same query.
        > 
        
        > However, using nested subqueries would have made
        the query harder to read and understand. The with clause makes the query logic clearer.
        > 
        
        > It also permits this temporary relation to be used in multiple places within a query.
        > 
    - Scalar Subqueries
        
        > SQL allows subqueries to occur wherever an expression returning a value is permitted, provided the subquery returns only one tuple containing a single attribute.
        > 
        
        > Scalar subqueries can occur in select, where, and having clauses.
        > 
        
        > Scalar subqueries may also be defined without aggregates.
        > 
    - Scalar Without a From Clause
        
        > Certain queries require a calculation but no reference to any relation. Similarly, certain queries may have subqueries that contain a from clause without the top-level query needing a from clause.
        > 
- Modification of the Database
    - Deletion
        
        > We can delete only whole tuples; we cannot delete values on only particular attributes.
        > 
        
        > The where clause can be omitted, in which case all tuples in r are deleted.
        > 
        
        > Note that a delete command operates on only one relation. If we want to delete tuples from several relations, we must use one delete command for each relation.
        > 
        
        > Although we may delete tuples from only one relation at a time, we may reference any number of relations in a select-from-where nested in the where clause of a delete. The delete request can contain a nested select that references the relation from which tuples are to be deleted.
        > 
        
        > The delete statement first apply the predicate in the where clause to filter the tuples, all tuples that pass the test, are deleted. Performing all the tests before performing any deletion is important, specially with aggregate functions like AVG(attribute), if we've deleted tuples before applying the predicate that filters them, the AVG(attribute) may change, which will lead to deleting wrong tuples.
        > 
    - Insertion
        
        > To insert data into a relation, we either specify a tuple to be inserted or write a query whose result is a set of tuples to be inserted.
        > 
        
        > The attribute values for inserted tuples must be members of the corresponding attribute’s domain. Similarly, tuples inserted must have the correct number of attributes.
        > 
        
        > The simplest insert statement is a request to insert one tuple.
        > 
        
        > We might want to insert tuples on the basis of the result of a query. Instead of specifying a tuple as we did earlier, we use a select to specify a set of tuples.
        > 
    - Updates
        
        > In certain situations, we may wish to change a value in a tuple without changing all values in the tuple.
        > 
        
        > The where clause can be omitted, in which case all tuples in r are updated.
        > 
        
        > As before, SQL first apply the predicate in the where clause to filter the tuples, all tuples that pass the test, are updated.
        > 
        
        > SQL provides a case construct that we can use to perform both updates with a single update statement, avoiding the problem with the order of updates.
        > 
        
        > Many systems support a coalesce function, which provides a concise way of replacing nulls by other values.
        >