# DBMS(Database Management System)

- used to store and retrieve data

- **Database** is collection of related data.
- **Data** is collection of facts and figures that can be processed to produce information.

- DBMS stores data in such a way that it becomes easier to retrieve,manipulate and produce info.

## Characteristics

- following are the characteristics of DBMS-

1. Real-world entity- Real world entities are used to design architecture. eg- school database has student as entity and age as attribute.
2. Relation-based tables- entities have relation among them to form a table
3. isolation of data and application- a database is active entity and data is passive, on which database works and organizes. DBMS also stores metadata.
4. Less redundancy
5. Consistency
6. Query language
7. ACID properties
8. Multiuser and Concurrent access
9. Multiple view
10. security

## Users

1. Administrators
2. Designers
3. End users

## Architecture

- 1-tier : only entity is DBMS.
- 2-tier : application is there through which DMS is accessed.
- 3-tier:

1. the 3 layers are- Database Tier, application Tier and Presentation tier.
2. In database tier the we have the database along with query processing languages.
3. In application tier we have th application server and the programs that access the database. it acts as a mediator between the end user and the database.
4. In presentation tier multiple views of the database is provided for different users.
   ![](https://www.tutorialspoint.com/dbms/images/dbms_architecture.png)

## Data Models

- defines the logical structure of database.

### Entity-relationship Model

- ER model is based on-

1. Entities and their attributes.
2. Relationship among entities.
3. ex- school database has student as entity and attributes are name,age,class,etc.
4. Logical association among entities is called **Relationship**.

### Relational Model

- based on first-order predicate logic.
- defines a table as an n-ary relation.
  ![](https://www.tutorialspoint.com/dbms/images/relational_model_table.png)

## Database Schema

- Structure that represents the logical view of the entire database.
- defines how data is organized.
- defines relations among data.
- formulates the constraints that are to be applied on the data.
- A database schema can be divided broadly into two categories:

1. Physical Database Schema: Defines how data will be stored in secondary storage. This schema pertains to the actual storage of data and its form of storage like files, indices,etc.

2. Logical Database Schema: Defines all the logical constraints that need to be applied on the data sorted. it defines tables, views and integrity constraints.
   ![](https://www.tutorialspoint.com/dbms/images/dbms_schemas.png)

## Database Instance

- It is a state of operational database with data at any given time.
- It contains a snapshot of the database.
- It tend to change with time.

## Data Independence

- Database system stores data about data, known as metadata, to locate and retrieve data easily.
- Metadata itself follows a layered architecture, so that when we change data at one layer, it does not affect the data at another level.
- This data is independent but mapped to each other.
  ![](https://www.tutorialspoint.com/dbms/images/data_independence.png)

### Logical data Independence

- It stores information about how data is managed inside database.
- Ex- a table(relation) stored in the database and all its constraints, applied on that relation.

### Physical Data Independence

- It is the power to change the physical data without impacting the schema or logical data.
- Ex- If we want to replace hard disk with SSD, it should ot have any impact on the logical data or schemas.

## ER Model-Basic Concepts

- ER Model defines the conceptual view of a database.

### Entity

- It can be a real-world object, either animate or inanimate.
- Ex- In a school database, students, teachers, classes, and courses offered can be considered as entities.
- An **entity set** is a collection of similar types of entities
- Ex- a Students set may contain all the students of a school; likewise a Teachers set may contain all the teachers of a school from all faculties.
- Entity sets need not be disjoint.

### Attributes

- Entities are represented by their properties, called attributes.
- Ex- a student entity may have name, class, and age as attributes.
- Types of attributes:

1. Simple attribute- a student's phone number is an atomic value of 10 digits
2. Composite attribute- a student's complete name may have first_name and last_name.
3. Derived attribute- average_salary in a department should not be saved directly in the database, instead it can be derived. Age can be derived from data_of_birth.
4. Single-value attribute- Social_Security_Number
5. Multi-value attribute- a person can have more than one phone number, email_address, etc.

### Keys

1. Candidate Key-

- Minimal set of attributes that can uniquely identify a tuple.
- Ex- ROLL_NO in STUDENT table.
- It is a minimal super key.
- It must contain unique values.
- It can contain NULL values
- Every table must at least have a single candidate key but can be more than one.
- Table can have multiple candidate key but only one primary key.

2. Primary Key

- There can be more than one candidate key in relation out of which one can be chosen as the primary key.
- Ex- ROLL_NO and STUD_PHONE, are candidate keys for relation STUDENT but ROLL_NO can be chosen as the primary key.
- It is a unique key.
- It can identify only one tuple (a record) at a time.
- It cannot be NULL.
- Primary keys are not necessarily to be a single column; more than one column can also be a primary key for a table.

3. Super Key

- The set of attributes that can uniquely identify a tuple is known as Super Key.
- A super key is a group of single or multiple keys that identifies rows in a table.
- Ex- STUD_NO, (STUD_NO, STUD_NAME), etc.
- It supports NULL values.
- A candidate key is a super key but vice versa is not true.

![](https://media.geeksforgeeks.org/wp-content/uploads/20230314093236/keys-in-dbms.jpg)

4. Alternate Key

- The candidate key other than the primary key is called an alternate key.
- Ex- SNAME, and ADDRESS is Alternate keys
  ![](https://media.geeksforgeeks.org/wp-content/uploads/20230314093606/Primary-key-alternative-key-in-dbms.png)

5. Foreign Key

- It combines two or more relations (tables) at a time.
- It is a key it acts as a primary key in one table and it acts as secondary key in another table.
- Ex- ID is primary key in STUDENT table and foreign key in MARKS table.

![](https://media.geeksforgeeks.org/wp-content/uploads/20230314173852/Foreign-keys.png)

6. Composite Key

- It acts as a primary key if there is no primary key in a table.
- Two or more attributes are used together to make a composite key.
- Ex- FULLNAME + DOB is used as composite key when there is no primary key.

**IMP QUES**
QUESTION: What is a Unique Key?
ANSWER: Unique Keys are the keys that define the record uniquely in the table. It is different from Primary Keys, as Unique Key can contain one NULL value but Primary Key does not contain any NULL values.

QUESTION: What is Artificial Key?
ANSWER: Artificial Keys are the keys that are used when no attributes contain all the properties of the Primary Key or if the Primary key is very large and complex.

### Relationship

- Association among entities.
- Ex- an employee **works_at** a department, a student **enrolls** in a course. Here, Works_at and Enrolls are called relationships.

### Mapping Cardinalities

- **Cardinality** defines the number of entities in one entity set,which can be associated with the number of entities of other set via relationship set.

1. One-to-one
   ![](https://www.tutorialspoint.com/dbms/images/one_to_one_relation.png)
2. One-to-many
   ![](https://www.tutorialspoint.com/dbms/images/one_to_many_relation.png)
3. Many-to-one
   ![](https://www.tutorialspoint.com/dbms/images/many_to_one_relation.png)
4. Many-to-many
   ![](https://www.tutorialspoint.com/dbms/images/many_to_many_relation.png)

## ER Diagram Representation

1. Entity

- Entities are represented by rectangles.
  ![](https://www.tutorialspoint.com/dbms/images/entities.png)

2. Attributes

- Attributes are represented by ellipses.
  ![](https://www.tutorialspoint.com/dbms/images/er_attributes.png)

- If the attributes are **composite**, they are further divided in a tree like structure.
  ![](https://www.tutorialspoint.com/dbms/images/er_attributes_composite.png)

- **Multivalued** attributes are depicted by double ellipse.
  ![](https://www.tutorialspoint.com/dbms/images/er_attributes_multivalued.png)

- **Derived** attributes are depicted by dashed ellipse.
  ![](https://www.tutorialspoint.com/dbms/images/er_attributes_derived.png)

3. Relationships

- Relationships are represented by diamond-shaped box.

4. Participation Constraints

- **Total Participation** − Each entity is involved in the relationship. Total participation is represented by double lines.
- **Partial participation** − Not all entities are involved in the relationship. Partial participation is represented by single lines.

![](https://www.tutorialspoint.com/dbms/images/er_relation_participation.png)

## ER Model Advanced Concepts

### Generalization

- Entities with similar characteristics are converted into one single general entity.
  ![](https://www.tutorialspoint.com/dbms/images/generalization.png)

### Specialization

- It is opposite of generalization.
- Group of entities is divided into sub-groups based on their characteristics.
  ![](https://www.tutorialspoint.com/dbms/images/specialization.png)

### Inheritance

- It allows lower-level entities to inherit the attributes of higher-level entities.
- Ex- the attributes of a Person class such as name, age, and gender can be inherited by lower-level entities such as Student or Teacher.
  ![](https://www.tutorialspoint.com/dbms/images/inheritance.png)

## Relation Data Model

- Primary data model.
- CONCEPTS:

1. **Tables** :

- Relations are saved in the format of Tables.
- A table has rows and columns, where rows represents records and columns represent the attributes.

2. **Tuple** :

- A single row of a table.

  3.**Relation instance** :

- A finite set of tuples.
- Relation instances do not have duplicate tuples.

4. **Relation schema** :

- A relation schema describes the relation name (table name), attributes, and their names.

5. **Relation key** :

- Each row has one or more attributes, known as relation key, which can identify the row in the relation (table) uniquely.

6. **Attribute domain** :

- Every attribute has some pre-defined value scope, known as attribute domain.

### Constraints

- There are three main integrity constraints −

#### Key Constraints

- There must be at least one minimal subset of attributes in the relation, which can identify a tuple uniquely.
- This minimal subset of attributes is called key for that relation.
- In a relation with a key attribute, no two tuples can have identical values for key attributes.
- A key attribute can not have NULL values.
- Key constraints are also referred to as Entity Constraints.

#### Domain Constraints

- There can be a specific range of values for a particular attribute.
- Ex- age can only be a positive integer, telephone numbers cannot contain a digit outside 0-9.

#### Referential integrity Constraints

- Referential integrity constraints work on the concept of Foreign Keys.
- Referential integrity constraint states that if a relation refers to a key attribute of a different or same relation, then that key element must exist.

## Relational Algebra

- Relational algebra is a procedural query language, which takes instances of relations as input and yields instances of relations as output.
- The fundamental operations of relational algebra are as follows −

### select Operation(σ)

- It selects the tuple that satisfy the condition from the table.
- Notation- σp(r), where σ stands for selection predicate and r stands for relation. p is prepositional logic formula which may use connectors like and, or, and not. These terms may use relational operators like − =, ≠, ≥, < , >, ≤.

**Examples**

1. σ subject = "database"(Books)
   OUTPUT- Selects tuples from books where subject is 'database'.
2. σ subject = "database" and price = "450" or year > "2010"(Books)
   OUTPUT- Selects tuples from books where subject is 'database' and 'price' is 450 or those books published after 2010.

### Project Operation (∏)

- It projects column(s) that satisfy a given predicate.
- Notation- ∏A1, A2, An (r), where A1, A2 , An are attribute names of relation r.

**Examples**

1. ∏subject, author (Books)
   OUTPUT- Selects and projects columns named as subject and author from the relation Books.

### Union Operation (U)

- It performs binary union between two given relations.
- Notation- r ∪ s = { t | t ∈ r or t ∈ s}, Where r and s are either database relations or relation result set (temporary relation).
- For a union operation to be valid, the following conditions must hold −

1. r, and s must have the same number of attributes.
2. Attribute domains must be compatible.
3. Duplicate tuples are automatically eliminated.

**Examples**

1. ∏ author (Books) ∪ ∏ author (Articles)
   OUTPUT- Projects the names of the authors who have either written a book or an article or both.

### Set Difference (−)

- The result of set difference operation is tuples, which are present in one relation but are not in the second relation.
- Notation − r − s, Finds all the tuples that are present in r but not in s.

**Examples**

1. ∏ author (Books) − ∏ author (Articles)
   OUTPUT- Provides the name of authors who have written books but not articles.

### Cartesian Product (Χ)

- Combines information of two different relations into one.
- Notation − r Χ s,where r and s are relations and their output will be defined as r Χ s = { q t | q ∈ r and t ∈ s}.

**Examples**

1. σ author = 'tutorialspoint'(Books Χ Articles)
   OUTPUT- Yields a relation, which shows all the books and articles written by tutorialspoint.

### Rename Operation (ρ)

- The rename operation allows us to rename the output relation.
- Notation − ρ x (E),where the result of expression E is saved with name of x.
- Additional operations are −

1. Set intersection
2. Assignment
3. Natural join

## Relational Calculus

- In contrast to Relational Algebra, Relational Calculus is a non-procedural query language, that is, it tells what to do but never explains how to do it.

- Relational calculus exists in two forms −

### Tuple Relational Calculus (TRC)

- Filtering variable ranges over tuples
- Notation − {T | Condition}, Returns all tuples T that satisfies a condition.

**Examples**

1. { T.name | Author(T) AND T.article = 'database' }
   OUTPUT- Returns tuples with 'name' from Author who has written article on 'database'.

- TRC can be quantified. We can use Existential (∃) and Universal Quantifiers (∀).

2. { R| ∃T ∈ Authors(T.article='database' AND R.name=T.name)}
   OUTPUT- Returns tuples with 'name' from Author who has written article on 'database'.

### Domain Relational Calculus (DRC)

- In DRC, the filtering variable uses the domain of attributes instead of entire tuple values.
- Notation − { a1, a2, a3, ..., an | P (a1, a2, a3, ... ,an)},where a1, a2 are attributes and P stands for formulae built by inner attributes.

**Examples**

1. {< article, page, subject > | ∈ TutorialsPoint ∧ subject = 'database'}
   OUTPUT- Yields Article, Page, and Subject from the relation TutorialsPoint, where subject is database.

## ER Model To Relational Model

- An ER Diagram has:

1. Entity and its attributes
2. Relationship, which is association among entities.

### Mapping entities

![](https://www.tutorialspoint.com/dbms/images/mapping_entities.png)

#### Mapping Process (Algorithm)

- Create table for each entity.
- Entity's attributes should become fields of tables with their respective data types.
- Declare primary key.

### Mapping Relationship

![](https://www.tutorialspoint.com/dbms/images/mapping_relationship.png)

#### Mapping Process

- Create table for a relationship.
- Add the primary keys of all participating Entities as fields of table with their respective data types.
- If relationship has any attribute, add each attribute as field of table.
- Declare a primary key composing all the primary keys of participating entities.
- Declare all foreign key constraints.

### Mapping Weak Entity Sets

- A weak entity set is one which does not have any primary key associated with it.

![](https://www.tutorialspoint.com/dbms/images/mapping_weak_entity_sets.png)

#### Mapping Process

- Create table for weak entity set.
- Add all its attributes to table as field.
- Add the primary key of identifying entity set.
- Declare all foreign key constraints.

### Mapping Hierarchical Entities

![](https://www.tutorialspoint.com/dbms/images/inheritance.png)

#### Mapping Process

- Create tables for all higher-level entities.
- Create tables for lower-level entities.
- Add primary keys of higher-level entities in the table of lower-level entities.
- In lower-level tables, add all other attributes of lower-level entities.
- Declare primary key of higher-level table and the primary key for lower-level table.
- Declare foreign key constraints.

## DBMS- Normalization

### Functional Dependency

- It is a set of constraints between two attributes in a relation.
- Functional dependency says that if two tuples have same values for attributes A1, A2,..., An, then those two tuples must have to have same values for attributes B1, B2, ..., Bn.
- Functional dependency is represented by an arrow sign (→) that is, X→Y, where X functionally determines Y.
- The left-hand side attributes determine the values of attributes on the right-hand side.
