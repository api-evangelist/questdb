<!-- fetched 2026-10-13 from https://questdb.com/docs/query/pgwire/overview/ by sweep-shape-compat.py; text extracted from the provider's own page -->

PostgreSQL Wire Protocol | QuestDB 
 For AI agents: the complete documentation index is at llms.txt . Every page is also available as markdown by appending .md to its URL, or by sending an Accept: text/markdown request header.
 Return to QuestDB.com Documentation Tutorials Blog QuestDB Enterprise Public Slack Discourse Community View QuestDB Repo 
 ⚡️ QuestDB Enterprise 10.0.1 | 17.4k Release Notes 
 Roadmap 
 Search 
 Introduction 
 Schema design 
 Getting Started 
 Connect 
 Overview 
 Client Libraries 
 Agents 
 Message Brokers 
 REST API 
 Compatibility Protocols 
 InfluxDB Line Protocol (ILP) 
 PostgreSQL Wire Protocol (PGWire) 
 Overview 
 Large Result Sets 
 Python 
 Go 
 Java 
 Rust 
 Node.js 
 .NET 
 PHP 
 R 
 C/C++ 
 Java Embedded 
 Wire Protocols 
 SQL Reference 
 Web Console 
 Concepts 
 Architecture 
 Configuration 
 Security 
 High Availability 
 Operations 
 Deployment 
 Integrations 
 Tutorials & Cookbook 
 Troubleshooting 
 Changelog 
 Release Notes 
 Connect 
 Compatibility Protocols 
 PostgreSQL Wire Protocol (PGWire) 
 Overview 
 On this page 
 PostgreSQL Wire Protocol
 Copy as Markdown 
 QuestDB implements the PostgreSQL wire protocol (PGWire), allowing you to
connect using standard PostgreSQL client libraries. This is the recommended way
to query data from QuestDB, as you can use existing PostgreSQL clients and
tools.
 PGWire also supports INSERT statements for lower-volume data
ingestion. For high-throughput ingestion, use the
 QuestDB clients instead.
 Query examples ​ 
 .NET
 Query QuestDB using Npgsql or other .NET PostgreSQL drivers.
 Read more 
 Go
 Query QuestDB using pgx or other Go PostgreSQL drivers.
 Read more 
 Java
 Query QuestDB using JDBC with any PostgreSQL-compatible driver.
 Read more 
 Node.js
 Query QuestDB using pg or other Node.js PostgreSQL clients.
 Read more 
 Python
 Query QuestDB using psycopg, asyncpg, or other Python drivers.
 Read more 
 Rust
 Query QuestDB using tokio-postgres or other Rust PostgreSQL crates.
 Read more 
 PHP
 Query QuestDB using PDO or other PHP PostgreSQL extensions.
 Read more 
 R
 Query QuestDB using RPostgres or other R database packages.
 Read more 
 Compatibility ​ 
 Supported features ​ 
 Querying (all types except BLOB )
 Prepared statements with bind parameters
 INSERT statements with bind parameters
 UPDATE statements with bind parameters
 DDL execution
 Batch inserts
 Plain authentication
 Unsupported features ​ 
 SSL
 Remote file upload ( COPY from stdin )
 DELETE statements
 BLOB transfer
 Connection properties ​ 
 Name
 Example
 Description
 database 
 qdb
 Can be set to any value (e.g., qdb ). Database name is ignored; QuestDB does not have database instance names.
 user 
 admin
 User name configured in pg.user or pg.readonly.user property in server.conf . Default: admin 
 password 
 quest
 Password from pg.password or pg.readonly.password property in server.conf . Default: quest 
 options 
 -c statement_timeout=60000
 The only supported option is statement_timeout , which specifies maximum execution time in milliseconds for SELECT or UPDATE statements.
 Important considerations ​ 
 Large result sets ​ 
 When querying large datasets, most PostgreSQL drivers load the entire result
set into memory before returning rows. This causes out-of-memory errors and
slow performance.
 Solution: Use cursor-based fetching to retrieve rows in batches.
 See Handling Large Result Sets for
per-language examples.
 Timestamp handling ​ 
 QuestDB stores all timestamps internally in
 UTC . However, when
transmitting timestamps over the PGWire protocol, QuestDB represents them as
 TIMESTAMP WITHOUT TIMEZONE . This can lead to client libraries interpreting
these timestamps in their local timezone by default, potentially causing
confusion or incorrect data representation.
 Our language-specific guides provide detailed examples on how to configure your
client to correctly interpret these timestamps as UTC.
 We recommend setting the timezone in your client library to UTC to ensure
consistent handling of timestamps.
 SQL dialect differences ​ 
 QuestDB's SQL dialect adds time-series clauses (SAMPLE BY, LATEST ON,
ASOF/LT/SPLICE/WINDOW/HORIZON joins, TICK intervals) and omits a small
number of standard features that do not fit a column-oriented, time-ordered
storage model ( DELETE , HAVING , OFFSET , DISTINCT ON , ON CONFLICT ,
correlated subqueries in WHERE ).
 For the full picture, including the QuestDB equivalent of each unsupported
feature, see
 SQL extensions and compatibility .
 Forward-only cursors ​ 
 QuestDB's cursors are forward-only, differing from PostgreSQL's support for
scrollable cursors (which allow bidirectional navigation and arbitrary row
access). With QuestDB, you can iterate through query results sequentially from
start to finish, but you cannot move backward or jump to specific rows.
 Explicit DECLARE CURSOR statements for scrollable types, or operations like
fetching in reverse (e.g., FETCH BACKWARD ), are not supported.
 This limitation can impact client libraries that rely on scrollable cursor
features. For example, Python's psycopg2 driver might encounter issues if
attempting such operations. For optimal compatibility, choose drivers or
configure existing ones to use forward-only cursors, such as Python's asyncpg
driver.
 Protocol flavors and encoding ​ 
 The PostgreSQL wire protocol has different implementations and options. When
your client library allows:
 Prefer the Extended Query Protocol over the Simple Query Protocol
 Choose clients that support BINARY encoding for data transfer over TEXT
encoding for optimal performance and type fidelity
 The specifics of how to configure this will vary by client library.
 Highly-available reads (Enterprise) ​ 
 QuestDB Enterprise supports running
 multiple replicas to serve queries. Many client
libraries allow specifying multiple hosts in the connection string. This
ensures that initial connections succeed even if a node is unavailable. If the
connected node fails later, the application should catch the error, reconnect to
another host, and retry the read.
 For background and code samples in multiple languages, see:
 Blog: Highly-available reads with QuestDB 
 Examples: questdb/questdb-ha-reads 
 INSERT examples ​ 
 PGWire supports INSERT statements for lower-volume ingestion use cases.
 psql
 Python
 Java
 NodeJS
 Go
 Rust
 Create the table:
 psql -h localhost -p 8812 -U admin -d qdb \ 
 -c "CREATE TABLE IF NOT EXISTS t1 (name STRING, value INT);" 
 Insert row:
 psql -h localhost -p 8812 -U admin -d qdb -c "INSERT INTO t1 VALUES('a', 42)" 
 Query back:
 psql -h localhost -p 8812 -U admin -d qdb -c "SELECT * FROM t1" 
 Note that you can also run psql from Docker without installing the client
locally:
 docker run -it --rm --network=host -e PGPASSWORD=quest \ 
 postgres psql .... 
 This example uses the psycopg3 
adapter.
 To install the
client library, use pip :
 python3 -m pip install "psycopg[binary]" 
 import psycopg as pg 
 import time 
 # Connect to an existing QuestDB instance 
 conn_str = 'user=admin password=quest host=127.0.0.1 port=8812 dbname=qdb' 
 with pg . connect ( conn_str , autocommit = True ) as connection : 
 # Open a cursor to perform database operations 
 with connection . cursor ( ) as cur : 
 # Execute a command: this creates a new table 
 cur . execute ( ''' 
 CREATE TABLE IF NOT EXISTS test_pg ( 
 ts TIMESTAMP, 
 name STRING, 
 value INT 
 ) timestamp(ts); 
 ''' ) 
 print ( 'Table created.' ) 
 # Insert data into the table. 
 for x in range ( 10 ) : 
 # Converting datetime into millisecond for QuestDB 
 timestamp = time . time_ns ( ) // 1000 
 cur . execute ( ''' 
 INSERT INTO test_pg 
 VALUES (%s, %s, %s); 
 ''' , 
 ( timestamp , 'python example' , x ) ) 
 print ( 'Rows inserted.' ) 
 #Query the database and obtain data as Python objects. 
 cur . execute ( 'SELECT * FROM test_pg;' ) 
 records = cur . fetchall ( ) 
 for row in records : 
 print ( row ) 
 # the connection is now closed 
 package com.myco; 
 import java.sql.*; 
 import java.util.Properties; 
 class App { 
 public static void main(String[] args) throws SQLException { 
 Properties properties = new Properties(); 
 properties.setProperty("user", "admin"); 
 properties.setProperty("password", "quest"); 
 properties.setProperty("sslmode", "disable"); 
 final Connection connection = DriverManager.getConnection( 
 "jdbc:postgresql://localhost:8812/qdb", properties); 
 connection.setAutoCommit(false); 
 final PreparedStatement statement = connection.prepareStatement( 
 "CREATE TABLE IF NOT EXISTS trades (" + 
 " ts TIMESTAMP, date DATE, name STRING, value INT" + 
 ") timestamp(ts);"); 
 statement.execute(); 
 try (PreparedStatement preparedStatement = connection.prepareStatement( 
 "INSERT INTO TRADES VALUES (?, ?, ?, ?)")) { 
 preparedStatement.setTimestamp( 
 1, 
 new Timestamp(io.questdb.std.Os.currentTimeMicros())); 
 preparedStatement.setDate(2, new Date(System.currentTimeMillis())); 
 preparedStatement.setString(3, "abc"); 
 preparedStatement.setInt(4, 123); 
 preparedStatement.execute(); 
 } 
 System.out.println("Done"); 
 connection.close(); 
 } 
 } 
 This example uses the pg package which
allows for quickly building queries using Postgres wire protocol. Details on the
use of this package can be found on the
 node-postgres documentation .
 This example uses naive Date.now() * 1000 inserts for Timestamp types in
microsecond resolution. For accurate microsecond timestamps, the
 process.hrtime.bigint() 
call can be used.
 "use strict" 
 const { Client } = require ( "pg" ) 
 const start = async ( ) => { 
 const client = new Client ( { 
 database : "qdb" , 
 host : "127.0.0.1" , 
 password : "quest" , 
 port : 8812 , 
 user : "admin" , 
 } ) 
 await client . connect ( ) 
 const createTable = await client . query ( 
 "CREATE TABLE IF NOT EXISTS trades (" + 
 " ts TIMESTAMP, date DATE, name STRING, value INT" + 
 ") timestamp(ts);" , 
 ) 
 console . log ( createTable ) 
 let now = new Date ( ) . toISOString ( ) 
 const insertData = await client . query ( 
 "INSERT INTO trades VALUES($1, $2, $3, $4);" , 
 [ now , now , "node pg example" , 123 ] , 
 ) 
 await client . query ( "COMMIT" ) 
 console . log ( insertData ) 
 for ( let rows = 0 ; rows < 10 ; rows ++ ) { 
 // Providing a 'name' field allows for prepared statements / bind variables 
 now = new Date ( ) . toISOString ( ) 
 const query = { 
 name : "insert-values" , 
 text : "INSERT INTO trades VALUES($1, $2, $3, $4);" , 
 values : [ now , now , "node pg prep statement" , rows ] , 
 } 
 await client . query ( query ) 
 } 
 await client . query ( "COMMIT" ) 
 const readAll = await client . query ( "SELECT * FROM trades" ) 
 console . log ( readAll . rows ) 
 await client . end ( ) 
 } 
 start ( ) 
 . then ( ( ) => console . log ( "Done" ) ) 
 . catch ( console . error ) 
 This example uses the pgx driver and toolkit for
PostgreSQL in Go. More details on the use of this toolkit can be found on the
 GitHub repository for pgx .
 package main 
 import ( 
 "context" 
 "fmt" 
 "log" 
 "time" 
 "github.com/jackc/pgx/v4" 
 ) 
 var conn * pgx . Conn 
 var err error 
 func main ( ) { 
 ctx := context . Background ( ) 
 conn , _ = pgx . Connect ( ctx , "postgresql://admin:quest@localhost:8812/qdb" ) 
 defer conn . Close ( ctx ) 
 // text-based query 
 _ , err := conn . Exec ( ctx , 
 ( "CREATE TABLE IF NOT EXISTS trades (" + 
 " ts TIMESTAMP, date DATE, name STRING, value INT" + 
 ") timestamp(ts);" ) ) 
 if err != nil { 
 log . Fatalln ( err ) 
 } 
 // Prepared statement given the name 'ps1' 
 _ , err = conn . Prepare ( ctx , "ps1" , "INSERT INTO trades VALUES($1,$2,$3,$4)" ) 
 if err != nil { 
 log . Fatalln ( err ) 
 } 
 // Insert all rows in a single commit 
 tx , err := conn . Begin ( ctx ) 
 if err != nil { 
 log . Fatalln ( err ) 
 } 
 for i := 0 ; i < 10 ; i ++ { 
 // Execute 'ps1' statement with a string and the loop iterator value 
 _ , err = conn . Exec ( 
 ctx , 
 "ps1" , 
 time . Now ( ) , 
 time . Now ( ) . Round ( time . Millisecond ) , 
 "go prepared statement" , 
 i + 1 ) 
 if err != nil { 
 log . Fatalln ( err ) 
 } 
 } 
 // Commit the transaction 
 err = tx . Commit ( ctx ) 
 if err != nil { 
 log . Fatalln ( err ) 
 } 
 // Read all rows from table 
 rows , err := conn . Query ( ctx , "SELECT * FROM trades" ) 
 fmt . Println ( "Reading from trades table:" ) 
 for rows . Next ( ) { 
 var name string 
 var value int64 
 var ts time . Time 
 var date time . Time 
 err = rows . Scan ( & ts , & date , & name , & value ) 
 fmt . Println ( ts , date , name , value ) 
 } 
 err = conn . Close ( ctx ) 
 } 
 The following example shows how to use parameterized queries and prepared
statements using the rust-postgres 
client.
 use postgres :: { Client , NoTls , Error } ; 
 use chrono :: { Utc } ; 
 use std :: time :: SystemTime ; 
 fn main ( ) -> Result < ( ) , Error > { 
 let mut client = Client :: connect ( "postgresql://admin:quest@localhost:8812/qdb" , NoTls ) ? ; 
 // Basic query 
 client . batch_execute ( 
 "CREATE TABLE IF NOT EXISTS trades ( \ 
 ts TIMESTAMP, date DATE, name STRING, value INT \ 
 ) timestamp(ts);" ) ? ; 
 // Parameterized query 
 let name : & str = "rust example" ; 
 let val : i32 = 123 ; 
 let utc = Utc :: now ( ) ; 
 let sys_time = SystemTime :: now ( ) ; 
 client . execute ( 
 "INSERT INTO trades VALUES($1,$2,$3,$4)" , 
 & [ & utc . naive_local ( ) , & sys_time , & name , & val ] , 
 ) ? ; 
 // Prepared statement 
 let mut txn = client . transaction ( ) ? ; 
 let statement = txn . prepare ( "INSERT INTO trades VALUES ($1,$2,$3,$4)" ) ? ; 
 for value in 0 .. 10 { 
 let utc = Utc :: now ( ) ; 
 let sys_time = SystemTime :: now ( ) ; 
 txn . execute ( & statement , & [ & utc . naive_local ( ) , & sys_time , & name , & value ] ) ? ; 
 } 
 txn . commit ( ) ? ; 
 println! ( "import finished" ) ; 
 Ok ( ( ) ) 
 } 
 Decimal values ​ 
 To insert decimal values via PGWire, you must either use the m suffix to
indicate that the value is a decimal literal or cast the value to decimal :
 INSERT INTO my_table (decimal_column) VALUES (123.45m); -- Using 'm' suffix 
 INSERT INTO my_table (decimal_column) VALUES (CAST($1 AS DECIMAL(18, 3))); -- Using CAST over bind parameter 
 In the text format, PostgreSQL clients send decimal values as strings.
Currently, QuestDB parses these strings as double values and doesn't
implicitly convert them to decimal to avoid unintended precision loss. You
must explicitly cast double values to decimal in your SQL queries when
inserting into decimal columns.
 Edit this page 
 Previous
 Advanced settings
 Next
 Large Result Sets
 Query examples 
 Compatibility Supported features 
 Unsupported features 
 Connection properties 
 Important considerations Large result sets 
 Timestamp handling 
 SQL dialect differences 
 Forward-only cursors 
 Protocol flavors and encoding 
 Highly-available reads (Enterprise) 
 INSERT examples Decimal values 
 Need a hand? Join our vibrant public Slack and Discourse forum communities.
 Copyright © 2026 QuestDB SOC 2 Type 1 Compliant Privacy Terms Cookie settings
