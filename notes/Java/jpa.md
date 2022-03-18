JPA stands for Java Persistence API.

It is a specification and not an implementation, it bridges the gap between object oriented programming and relational databases.

If an object contains another object, then we call it HAS-A relationship through encapsulation.

If an object is a specialization of another object, then IS-A relationship through inheritance.

Entities -> Entity is a marker annotation, that is used to discover persistence entities, if we want to make a class as an entity then we have to annotate that class with @Entity. That class will be mapped to the table in database.

After defining the entity class, the next thing is to define its fields, which are the member variables of class, by default these are mapped to the table with column names same as field names, but if we want to change the name of the column name then we have to use @Column annotation and specify the name.

>> Caching is the advantage of JPA to use over other frameworks. What is caching? Which means the JPA quries will only hit the database once and for repeated query JPA itself returns the data.


@JoinColumn can be used to specify the name of the column in the table.

Relationships between entities

-> OneToOne

This annotation is used to define one to one relationships between two entities. consider a User entity which contains username password fields and there is an other entity which has age, gender fields. One to one relationship helps to map the relation between two entities.

-> OneToMany or ManyToOne

These annotations maps both sides of same relationship. Consider a person can have any number of vehicles then it is @OneToMany relation ship and many vehicles can have only one owner or user then it is a @ManyToOne relationship


-> ManyToMany facilitates a many to many relationship between entities.
where multiple books written by multiple authors.


	JoinColumns and inverseJoinColumns attributes tells the jpa framework to how to map the many to many relationship.

 >> EntityManager is the class that performs the database interaction in JPA. It is initialized through a configuration file called persistence.xml. Which is present in the META-INF folder in the class path.
This file contains the information or collection of properties that specifies how to connect to the database.

To use the entity manager class we have to create that using EntityManagerFactory using Persistence class.

>> The EntityManager class defines how to interact to the database through entities. The methods of entity manager class are.

-> find retrieves an entity by its primary key.
-> createQuery creates a Query instance that can be used to retrieve entities from the database.

-> createNamedQuery loads a Query that has been defined in a @NamedQuery annotation inside one of the persistence entities. Named queries provide a clean mechanism for centralizing JPA queries in the definition of the persistence class on which the query will execute.

-> getTransaction defines an EntityTransaction to use in your database interactions. Just like database transactions, you will typically begin the transaction, perform your operations, and then either commit or rollback your transaction. The getTransaction() method lets you access this behavior at the level of the EntityManager, rather than the database.

-> merge() adds an entity to the persistence context, so that when the transaction is committed, the entity will be persisted to the database. When using merge(), objects are not managed.
persist adds an entity to the persistence context, so that when the transaction is committed, the entity will be persisted to the database. When using persist(), objects are managed.

-> refresh refreshes the state of the current entity from the database.

->flush synchronizes the state of the persistence context with the database.


>> JPQL 
JPQL is similar to SQL, but it operates on entities, their fields and their relationships, rather than on database column names.


  >> SELECT * FROM BOOK (SQL) is as same as SELECT b FROM BOOK b (JPQL)


 >> Query interface needs to be used when the query result type is unknown.
 >> Merge, Detach and Remove are valid cascade types.
 >> 