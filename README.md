# Databases in Simple Terms

Making an informed decision of what database to use for your next web application is hard. This document attempts to make it easier.

Issues and/or pull requests are highly encouraged to make this document better as long as we can keep it somewhat simple and easy to look over.

### Definitions

Each database is optimized differently for how you want to read and write data and how you want it to handle problems and scaling. These definitions help you understand those differences.

**Query language**: A specialized language for requesting or modifying data in a database, often expressing relationships or structure of that data. Not all databases utilize a query language at all.

**Schema**: A specification of the structured data that will go into your database used to determine how the database is organized/optimized and/or how data is validated when being written to it.

**Object-relational mapping** or **ORM**: A technique which provides a layer between your application and your database to convert objects into database queries.

**Relational database**: A database structured with tables and columns to express the relationship between its data. Most relational databases use SQL as their query language.

**Object-relational database**: A relational database which allows you to treat tables like data structures in an object-oriented language, such as with objects, classes, and inheritance.

**Graph database**: A database using graph structures with nodes and edges to represent data points and the relationships/interconnections between them.

**Document-oriented database** or **document store**: A type of database in which each record and its associated data is thought of as a loosely defined "document" rather than a strictly defined structure.

**Key-value store**: A simple database with a 1:1 relationship between keys and values, like a hash table. This isn't to say that more complex relationships and query languages can't be built on top of the store.

**Horizontal/vertical scaling**: Scaling horizontally means adding more machines, such as replicating or sharding a database. Scaling vertically means adding more resources (CPUs, RAM) to a single machine.

**Distributed database**: A database which may be stored on multiple computers which need not be in the same location but must periodically synchronize to maintain data consistency.

**Replication**: Duplicating a whole database across multiple machines/locations which must then be synchronized. May be in a master-slave configuration in which all nodes can be read from but only a master node handles writes, or in a multi-master configuration where all nodes can be read from and written to. Multi-master replication introduces more complexities such as handling conflicting concurrent write operations.

**Sharding**: Breaking up a single database in multiple smaller databases which do not share their data. This is used for databases which may be too large to fit on one machine or for databases which benefit from querying only part of the data such as accessing customer data by country.

**Transaction**: An "all-or-nothing" operation on a database which must follow ACID rules.

**ACID**:
- **Atomicity**: Ensures every operation within a transaction succeeds or otherwise none of them are written to the database.
- **Consistency**: Ensures the transaction does not leave the database in an invalid state, such as an order to a product which does not exist.
- **Isolation**: Ensures a transaction not yet complete does not affect any other transaction.
- **Durability**: Ensures that data is saved in such a way that in any event, even power failure, committed data will always be stored permanently and correctly.

**Embedded database**: A database which is built into an application instead of running seperately.



# Popular Databases



## RethinkDB

Distributed document-oriented database with its own query language known as [ReQL](https://www.rethinkdb.com/docs/introduction-to-reql/).

[![Website](https://img.shields.io/badge/website-rethinkdb.com-blue.svg?maxAge=2592000)](https://www.rethinkdb.com/)


#### Good for:

> Use cases where companies benefited from RethinkDB’s realtime push architecture include:
> - Collaborative web and mobile apps
> - Streaming analytics apps
> - Multiplayer games
> - Realtime marketplaces
> - Connected devices
>
> — [Official FAQ](https://www.rethinkdb.com/faq/)

> So in simple terms RethinkDB will be best suited when you have real time data coming in and you want that data to continuously refresh in your front end for the users to see. Examples which can use RethinkDB as their back-end can be a stock market application or a multiplayer game.
>
> — [Getting Started with RethinkDB in Nodejs](http://www.codingdefined.com/2016/09/getting-started-with-rethinkdb-in-nodejs.html)

#### Tradeoffs:

>  When is RethinkDB not a good choice?
> - RethinkDB is not a good choice if you need full ACID support or strong schema enforcement—in this case you are better off using a relational database such as MySQL or PostgreSQL.
> - If you are doing deep, computationally-intensive analytics you are better off using a system like Hadoop or a column-oriented store like Vertica.
> - In some cases RethinkDB trades off write availability in favor of data consistency. If high write availability is critical and you don’t mind dealing with conflicts you may be better off with a Dynamo-style system like Riak.
>
> — [Official FAQ](https://www.rethinkdb.com/faq/#when-is-rethinkdb-not-a-good-choice)



## PostgreSQL

Advanced SQL-compliant object-relational database.

[![Website](https://img.shields.io/badge/website-postgresql.org-blue.svg?maxAge=2592000)](https://www.postgresql.org/)

#### Good for:

[Make an issue or pull request!]

#### Tradeoffs:

[Make an issue or pull request!]


## MySQL

A relational database popular for it's ease of use.

[![Website](https://img.shields.io/badge/website-mysql.com-blue.svg?maxAge=2592000)](https://www.mysql.com/)


#### Good for:

[Make an issue or pull request!]

#### Tradeoffs:

[Make an issue or pull request!]


## Neo4j

"An ACID-compliant transactional database with native graph storage and processing"

[![Website](https://img.shields.io/badge/website-neo4j.com-blue.svg?maxAge=2592000)](https://neo4j.com/)


#### Good for:

[Make an issue or pull request!]

#### Tradeoffs:

[Make an issue or pull request!]


## MongoDB



[![Website](https://img.shields.io/badge/website-mongodb.com-blue.svg?maxAge=2592000)](https://www.mongodb.com/)


#### Good for:

[Make an issue or pull request!]

#### Tradeoffs:

[Make an issue or pull request!]


## CouchDB

"Apache CouchDB™ is a database that uses JSON for documents, JavaScript for MapReduce indexes, and regular HTTP for its API"

[![Website](https://img.shields.io/badge/website-couchdb.apache.org-blue.svg?maxAge=2592000)](https://couchdb.apache.org/)


#### Good for:

[Make an issue or pull request!]

#### Tradeoffs:

[Make an issue or pull request!]


## SQLite3

Embedded relational database.

[![Website](https://img.shields.io/badge/website-sqlite.org-blue.svg?maxAge=2592000)](https://www.sqlite.org/)


#### Good for:

[Make an issue or pull request!]

#### Tradeoffs:

[Make an issue or pull request!]
