# Databases in Simple Terms

Making an informed decision of what open source database to use for your next web application is hard. This document attempts to make it easier.

Issues and/or pull requests are highly encouraged to make this document better as long as we can keep it somewhat simple and easy to look over.

### Definitions

Each database is optimized differently for how you want to read and write data and how you want it to handle problems and scaling. These definitions help you understand those differences.

**Query language**: A specialized language for requesting or modifying data in a database, often expressing relationships or structure of that data. Not all databases utilize a query language at all.

**Schema**: A specification of the structured data that will go into your database used to determine how the database is organized/optimized and/or how data is validated when being written to it. A schema-less database makes it your own responsibility to ensure data consistency.

**Object-relational mapping** or **ORM**: A technique which provides a layer between your application and your database to convert objects into database queries.

**Relational database**: A database structured with tables and columns to express the relationship between its data. Most relational databases use SQL as their query language.

**Object-relational database**: A relational database which allows you to treat tables like data structures in an object-oriented language, such as with objects, classes, and inheritance.

**Wide column store** or **extensible record store**: A database organized into tables but where each row can contain an arbitrarily large number of columns.

**Column-oriented database**: A database which stores data grouped by column rather than by row as a traditional relational database would. This way querying a single column of every entry in a table effeciently reads just the column instead of having to scan each entry and discard other columns. The tradeoff is that updates/deletes to entries are slower as they have to write to each column individually.

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

We're listing popular/useful free databases in order of their popularity score on [db-engines.com](http://db-engines.com/en/ranking).

## MySQL

A relational database popular for its ease of use and extensive use in the industry.

[![Website](https://img.shields.io/badge/website-mysql.com-blue.svg?maxAge=2592000)](https://www.mysql.com/)

Note that MySQL has multiple storage engines you can choose from with different performance/use cases. The default and most commonly used is InnoDB.

#### Good for:

[What types of applications best utilize its performance or other attributes and why? Make an issue or pull request!]

#### Tradeoffs:

> - It’s Got A Few Stability Issues
> - It Suffers From Relatively Poor Performance Scaling
> - Development Is Not Community Driven – and Hence Has Lagged
> - Its Functionality Tends To Be Heavily Dependant On Addons
> - Developers May Find Some Of Its Limitations To Be Frustrating
> 
> — [Five Advantages & Disadvantages Of MySQL](https://www.datarealm.com/blog/five-advantages-disadvantages-of-mysql/)


## PostgreSQL

Advanced SQL-compliant object-relational database.

[![Website](https://img.shields.io/badge/website-postgresql.org-blue.svg?maxAge=2592000)](https://www.postgresql.org/)

#### Good for:

[What types of applications best utilize its performance or other attributes and why? Make an issue or pull request!]

#### Tradeoffs:

> - For simple read-heavy operations, PostgreSQL can be an over-kill and might appear less performant than the counterparts, such as MySQL.
> - Unless you require absolute data integrity, ACID compliance or complex designs, PostgreSQL can be an over-kill for simple set-ups.
>  - Replication: Unless you are willing to spend the time, energy and resources, achieving replication with [PostgreSQL,] MySQL might be simpler for those who lack the database and system administration experience.
>  
>  — [Digital Ocean - SQLite vs MySQL vs PostgreSQL: A Comparison Of Relational Database Management Systems](https://www.digitalocean.com/community/tutorials/sqlite-vs-mysql-vs-postgresql-a-comparison-of-relational-database-management-systems)


## MongoDB

Document-oriented database popular for being easy to start with and being in the well known MEAN stack.

[![Website](https://img.shields.io/badge/website-mongodb.com-blue.svg?maxAge=2592000)](https://www.mongodb.com/)


#### Good for:

[What types of applications best utilize its performance or other attributes and why? Make an issue or pull request!]

#### Tradeoffs:

[What situations is it not optimized for? Make an issue or pull request!]


## Cassandra

Distributed database with a focus on master-master replication.

[![Website](https://img.shields.io/badge/website-cassandra.apache.org-blue.svg?maxAge=2592000)](https://cassandra.apache.org/)

#### Good for:

[What types of applications best utilize its performance or other attributes and why? Make an issue or pull request!]

#### Tradeoffs:

[What situations is it not optimized for? Make an issue or pull request!]


## SQLite

Embedded relational database.

[![Website](https://img.shields.io/badge/website-sqlite.org-blue.svg?maxAge=2592000)](https://www.sqlite.org/)


#### Good for:

[What types of applications best utilize its performance or other attributes and why? Make an issue or pull request!]

#### Tradeoffs:

[What situations is it not optimized for? Make an issue or pull request!]


## Redis

In-memory (but persisted to disk) key-value store wherein values can contain more complex data structures for complex yet very efficient queries.

[![Website](https://img.shields.io/badge/website-redis.io-blue.svg?maxAge=2592000)](http://redis.io/)

#### Good For:

> - Show latest items listings in your home page
> - Deletion and filtering
> - Leaderboards and related problems
> - Order by user votes and time
> - Implement expires on items
> - Counting stuff
> - Unique N items in a given amount of time
> - Real time analysis of what is happening, for stats, anti spam, or whatever
> - Pub/Sub
> - Queues
> - Caching
> 
> — [High Scalability - 11 Common Web Use Cases Solved In Redis](http://highscalability.com/blog/2011/7/6/11-common-web-use-cases-solved-in-redis.html)
	
#### Tradeoffs:

> Redis is an in-memory but persistent on disk database, so it represents a different trade off where very high write and read speed is achieved with the limitation of data sets that can't be larger than memory.
> 
> — [Redis FAQ](http://redis.io/topics/faq)


## Elasticsearch

Distributed, document-oriented full-text search engine.

[![Website](https://img.shields.io/badge/website-elastic.co/products/elasticsearch-blue.svg?maxAge=2592000)](https://www.elastic.co/products/elasticsearch)

#### Good for:

> Elasticsearch builds distributed capabilities on top of Apache Lucene to provide the most powerful full- text search capabilities available. Powerful, developer-friendly query API supports multilingual search, geolocation, contextual did-you-mean suggestions, autocomplete, and result snippets.
> q
> — [Website](https://www.elastic.co/products/elasticsearch)

[What types of applications best utilize its performance or other attributes and why? Make an issue or pull request!]

#### Tradeoffs:

[What situations is it not optimized for? Make an issue or pull request!]


## MariaDB

Relational database forked from and compatible with MySQL but with further enhanced capabilities.

[![Website](https://img.shields.io/badge/website-mariadb.org-blue.svg?maxAge=2592000)](https://mariadb.org/)

#### Good for:

[What types of applications best utilize its performance or other attributes and why? Make an issue or pull request!]

#### Tradeoffs:

[What situations is it not optimized for? Make an issue or pull request!]


## Neo4j

Transactional graph database using the [Cypher query language](http://neo4j.com/docs/stable/cypher-introduction.html).

[![Website](https://img.shields.io/badge/website-neo4j.com-blue.svg?maxAge=2592000)](https://neo4j.com/)


#### Good for:

[What types of applications best utilize its performance or other attributes and why? Make an issue or pull request!]

#### Tradeoffs:

[What situations is it not optimized for? Make an issue or pull request!]


## Couchbase


## Memcached


## CouchDB

Dcoument-oriented database "built for the web" using JavaScript as a query language and versioning data to prevent conflicting concurrent writes from overwritting one another.

[![Website](https://img.shields.io/badge/website-couchdb.apache.org-blue.svg?maxAge=2592000)](https://couchdb.apache.org/)

#### Good for:

[What types of applications best utilize its performance or other attributes and why? Make an issue or pull request!]

#### Tradeoffs:

[What situations is it not optimized for? Make an issue or pull request!]


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



## LevelDB

Embedded, low-level key-value store. A number of other databases build a higher level abstraction on top of leveldb.

[![Website](https://img.shields.io/badge/website-github.com/google/leveldb-blue.svg?maxAge=2592000)](https://github.com/google/leveldb)

Note that in the Node.js ecosystem [LevelUP](https://github.com/Level/levelup/#levelup) provides an API for LevelDB which can use [other backends and has numerous plugins](https://github.com/Level/levelup/wiki/Modules#modules) which can extend its functionality with complex operations.

#### Good for:

[What types of applications best utilize its performance or other attributes and why? Make an issue or pull request!]

#### Tradeoffs:

[Is LMDB a LevelDB Killer?](https://symas.com/is-lmdb-a-leveldb-killer/) (Summarize?)

> LevelDB is widely noted for being unreliable and databases it manages are prone to corruption. Academic studies of past versions of LevelDB have found that, under some file systems, the data stored in those versions of LevelDB might become inconsistent after a system crash or power failure. LevelDB corruption is so commonplace that corruption detection has to be built in to applications that use it.
> 
> — [Wikipedia](https://en.wikipedia.org/wiki/LevelDB#Bugs_and_reliability)


## RocksDB

Embedded key-value store forked from LevelDB to improve performance for different use cases.

[![Website](https://img.shields.io/badge/website-rocksdb.org-blue.svg?maxAge=2592000)](http://www.rocksdb.org/)

#### Good for:

[What types of applications best utilize its performance or other attributes and why? Make an issue or pull request!]

#### Tradeoffs:

[What situations is it not optimized for? Make an issue or pull request!]


## LMDB

Embedded, transactional, memory-mapped key-value store.

[![Website](https://img.shields.io/badge/website-symas.com/mdb-blue.svg?maxAge=2592000)](http://symas.com/mdb)

#### Good for:

[What types of applications best utilize its performance or other attributes and why? Make an issue or pull request!]

#### Tradeoffs:

[Is LMDB a LevelDB Killer?](https://symas.com/is-lmdb-a-leveldb-killer/) (Summarize?)

[What situations is it not optimized for? Make an issue or pull request!]


[more?]
