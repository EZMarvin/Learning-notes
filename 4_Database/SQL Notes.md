NEW STUFF on SQL Server
=============
###  <font color = darkblue>In-Memory OLTP</font>
In-Memory OLTP (online transaction processing) can improve the performance of transaction processing, data load.

It use No locks, no internal latches.

Engine makes new version of rows and timestamp of rows in shared buffer, analyzes and validate before committing. 

是real time system 快速响应，OLTP 数据库旨在使事务应用程序仅写入所需的数据，以便尽快处理单个事务。

支持大量并发用户定期添加和修改数据。

反映随时变化的单位状态，但不保存其历史记录。

包含大量数据，其中包括用于验证事务的大量数据。

结构复杂。

可以进行优化以对事务活动做出响应。

提供用于支持单位日常运营的技术基础结构。

个别事务能够很快地完成，并且只需访问相对较少的数据。OLTP 旨在处理同时输入的成百上千的事务。

实时性要求高。

数据量不是很大。

交易一般是确定的，所以OLTP是对确定性的数据进行存取。(比如存取款都有一个特定的金额)
并发性要求高并且严格的要求事务的完整、安全性。(比如这种情况：有可能你和你的家人同时在不同的银行取同一个帐号的款)。

OLTP (On-line Transaction Processing) is involved in the operation of a particular system. OLTP is characterized by a large number of short on-line transactions (INSERT, UPDATE, DELETE). The main emphasis for OLTP systems is put on very fast query processing, maintaining data integrity in multi-access environments and an effectiveness measured by number of transactions per second. In OLTP database there is detailed and current data, and schema used to store transactional databases is the entity model (usually 3NF). It involves Queries accessing individual record like Update your Email in Company database.

OLAP (On-line Analytical Processing) deals with Historical Data or Archival Data. OLAP is characterized by relatively low volume of transactions. Queries are often very complex and involve aggregations. For OLAP systems a response time is an effectiveness measure. OLAP applications are widely used by Data Mining techniques. In OLAP database there is aggregated, historical data, stored in multi-dimensional schemas (usually star schema). Sometime query need to access large amount of data in Management records like what was the profit of your company in last year.

### <font color = darkblue>Temporal Tables</font> 
Temporal table is type table that provides correct information about stored facts at any point in time.

Two table inside - current data and historial data. current data change then store in the historial table

BASIC 
=============
### Database 
- Organized collection of logically related data

### DBMS - database management system
- software package for defining and managing database

### SQL SERVER Service? 
-  It receive the queries and **execute** them, send **response** back to calling applications.
-  Manage the **data files**

### SQL SERVER Agent?
- Automation service that manages the scheduled execution **task**
- **Notify** the administrators of problem occur

### SQL SERVER Profiler?
Interface to create and manage **traces** and analyze and replay trace result

### SQL SERVER Analyzer, Tuning Advisor?
Automatic database tuning **insight into query performance** problem, recommend solution and automatically fix problem 

### SQL SERVER Execution Plans
- Shows how SQL SERVER compile/executes the querys
- Read the executuation plan

### SQL SERVER Instance
- Database engine is complete DB server, one computer can have many instance, but only one default
- Every instance have its own copy of server files, databases

### Result set
set of record not only data also metadata like col name, datatype and sizes, **saved in ram**

### Object
Table, schema, db use to store or reference data

### Schema
collection of objects have db schema and table schema

### SQL SERVER SYSTEM DB
    - master (keep track of server installation, keeps information about disk space, file location, system configuration setting, login accounts)
    - model (template database, use as model to create new database)
    - tmpdb (used as workspace, store tmp table, used for worktable that will hold intermediate results, recreate everytime server restarted) **size is important for performance**
    - mssql (resource hidden, store procedure, functions)
    - msdb (used by SQL agent service, perform scheduled activities such as replication, backup and service broker)

### DataBase files
- primary data files: keeps track of all the rest files in database .mdf
- Secondary data files: can have zero or more. ndf
- Log files: every data base has at lease one log file that contains info to recover all transactions in a database. ldf

### T-SQL - transact - sql
is a programming language used in sql server for querying and modifying data and managing database

### Statements
    DDL -> 增删改查object table/db create object in db(data define)
    DCL -> who can see and modify data 权限 determine who can see or modify the data(data control)
    DML -> 增删改查表数据(in object) query and modify data in table (data manipulation)

### Result set
is a set of data that return by select, sp or function. could be empty or not

### Batch
is a group of one or more sql statement sent at same time for execution.

sql serve compilers the statement of a batch into a single executable unit, called executiion plan. statements in the execution plan are executed at a time.

    GO -> not statement, send current batch
    EXEC -> execute function procedure

### Identifiers, variables
    标识符 128 character 
    start with character
    [ 有括号，关键字]

    @ local variable and parameter
    @@ global variable (system use, system defined function)
    @@error / @@rowcount
    # temporary table / procedure
    ## global temporary table or other object
### data type
    * int tiny 1  small 2 big 8 
    * char varchar nvarchar
    * bit 
    * text (no union)
    * float real
    * decimal numberic (5,2) 123.45
    * date small date(min) date time(3.33ms) date time 2
    * money
    * time stamp 
    * SQL_VarIant 不定类型
### Flow-control, Statement block
```sql
    if ()begin end 
    else begin end

    while () begin end

    if ()
    goto name1
    name1:
        select ....
    
    select a, b = 
        case c
            when '' then ''
            when '' then '' 
            else ''
        end
    from ...
```
Queries
=============
### JOIN
    querying from more than one table and views
    inner join 0 - smaller(a,b)
    outter join - left right full - bigger(a,b) - a+b
    cross join Cartesian 卡提振
### from + where

### group by + having

### order by + top

### select [col...] into [new_table] from [table]
    only copy data, no constraint, index depend on table
### insert [into] tablename (col...) values (...)

### set identity_insert tablename [on | off]

### insert tablename (select ...)

### update <tablename> set <colname = value, ....> where < >
```sql
    UPDATE dbo.Table2   
    SET dbo.Table2.ColB = dbo.Table2.ColB + dbo.Table1.ColB  
    FROM dbo.Table2   
        INNER JOIN dbo.Table1   
    ON (dbo.Table2.ColA = dbo.Table1.ColA);  
```
### delete [from] tablename where condition
```sql
    DELETE Production.ProductProductPhoto 
    FROM Production.Example_ProductProductPhoto ppp 
    LEFT OUTER JOIN Production.Product p 
    ON ppp.ProductID = p.ProductID 
    WHERE p.ProductID IS NULL 
```
### difference truncate , drop and delete
truncate table tablename

| tuncate    | delete   |
| -------- | -----  |
| DDL      | DML   |
| lock table remove all records |   row lock for remove   |
| NO where | use where |  234  |
| minimal log so quick| maintain log so slower |
| reset identity col| retain the identity |

DROP
    
    remove table from db
    all rows/ index/ privilege removed
    no DML trigger
    no roll back ???
    DDL

### Subquery
    select in select connect with condition <>= exists all any in
### corrlated subq
    inner subquery use values from outer query
### union and union all / except / intercept
    combine data vertically

### JOIN VS SUBQ
    no certain answer
    join for return rows
    sub for return few rows

### Rank, row number, dense rank,
```sql
    rank() over (partition by order by) as rank 1134 排名
    row_number() over (...) as rownumber 1234 行数
    dense_number() over (...) as densenumber 11234 排名 紧凑

```

### Identity col
    a column that db made up by the value generate by db
    create..
    (
        id type identity(start, increment),
    )
### Constraints
    
    NOT NULL

    PRIMARY key have values that uniquely identify a row in a table (only one, no null, unique) 

    composite primary key is table constraint (two or more)

    unique (one null, can be fk) 

    candidate key not pk but can be (unique and no null)

    foreign key is col or combination of col used to establish link between two table
        delete key which fk point to - on delete
            * no action - error
            * cascade - delete reference fk row
            * set null - set to null fk row
            * set default - set to default fk row

    check limit value by accept by col logic expression
    constraint ck check (col < ....)
### Integrities 
    * Domain
        - all col in db must declare upon a defined domain
    * Entity
        - pk constraint unique and not null
    * Referential
        - FK constraint change can not make where fk point to

### Normalization 
    reduce redundacy ensure consistency

    save place/ avoid restructing/ increase flexibility 
    - Fist normal Form
        no same col , no repeating value, atomic value 
        无重复
    - Second 
        non-prime attribute is dependent on any proper subset of any candidate key
        非码列 完全依赖 键列
    - third 
        all the attributes in a table are determined only by the candidate keys of that relation and not by any non-prime attributes
        非码列 之间不能有完全依赖

### Exception handling

```sql
        begin try
        end try
        begin catch
        end catch
```


VIEW and TABLE
=============
### **SQL SERVER CTE** 
    common table expression (常用表表示) 
    * Temporary named result set
    * Defined within the execution scope of single DML statement
    * can be defined in Functions, Store Procedure, Triggers, View

- Syntax
    ```sql
    With <name> (colname.....)
    AS
    (
        Select from group by...
        No order by unless with top 
        NO INTO
    ), <name>
    AS
    (
        anchor memeber
        union all / union / Intersect / except
        anchor member
        union all
        recursive member (no distinct, group by, having, out join, top, subquery)
    )
    Select from <name> ....
    ```

- Example
    
    选出一个人以及他的所有下级
    ```sql
    WITH tmp 
    AS (
        select empid, mgid
        from employee where empid = 3
        Union all
        select e.empid, e.mgid
        from employee e 
        join tmp t on e.mgid = t.empid
    )
    select * 
    from tmp
    ```
- Usage
    * Used for recursive query 
    * Replace VIEW when use of view is not required, don't need to store metadata
    * Readability, easy to read and maintance

- Why use
    * Improve readability and manageability of complex querys
- Why not use

### **View** 

    Virtual table and content is defined by queries
    view of data of one or more tables in the database
        * regular view
        * index view (with clustered index)
        * distributed partitioned view (accross sql server instance)

- Syntax
    ```sql
    Create View <name> (cols...)
    AS (
        select distinct 
        from 
        Join
        NO order by 
        NO into
        NO temporary table or table variable
    )
    ```
- Example
    
- Usage

- Why use
    * Simplify data manipulation, frequently used, no need everytime
    * Hide structure of table, backward compatible interface
    * Customize data for user, no need permission
    * distribute querues.....combine data from different database

- Why not use

### **Table/ Temporary Table**
    
    Table is collection of data organized in certain way
    Temporary table defined like regular table, just store in tempdb
        **local temporary table #table**
            for current user use, 
            multiple connection can have same name,
            destory after sp finished(in store procedure the sp finished then drop),
            destory at end of session,(当前的不用了)

        **global temporary table ##table**
            anyuser with permission can use
            multiple connections share same temp table, no same name,
            dropped when session that create the table end and all other task have stop referencing (都不用了) 
    
- Syntax
    ```sql
    Create Table <name> / #<temp table>
    (
        id type constraints,
        id ....
        constraint check
    )
    ```

- Example
    
    ```sql

    ```
- Usage

- Why use

- Why not use

### **Temporary Variable**
    
    data type that can be used within batch, store procedure, function
    NO indexs
    NO FK
    YES pk/unique/check/null/not null 
    
- Syntax
    ```sql
    declare @name table
    (
        id type constraint
    )
    ```
- Example
    ```sql

    ```
- Usage
    * replace temp table, tmp table have performance problem
    * scope last duration of the batch, function, store procedure
- Why use
    * tmp table may cause overhead of tmpdb or store procedure recomplication
    * short lock time
    * less recomplication 
- Why not use
    * performance suffer when result set is too large





Transaction, SP, function
=============
### **Transaction** 
    recoverable logic unit of work
        commit - saved
        rollback - undone

    Transaction mode 
        - implicit transactions
            start new transaction after current transaction commit or rollback
        - explicit transactions
            explicitly define both start and end of transaction

    @@trancount - depth of the executed begin trans block

set savepoint - 
```sql
        begin transaction
        save {transaction | tran} savepoint_name
        ....
        if @@error <> 0 
            rollback transaction savepoint_name
        
        commit transaction
```
- Syntax
    ```sql
    Begin transation
    commit
    rollback
    ```
- Example
    
    ```sql
    DECLARE @TranName VARCHAR(20);  
    SELECT @TranName = 'MyTransaction';  

    BEGIN TRANSACTION @TranName;  
    USE AdventureWorks2012;  
    DELETE FROM AdventureWorks2012.HumanResources.JobCandidate  
    WHERE JobCandidateID = 13;  

    COMMIT TRANSACTION @TranName;  
    GO  
    ```
- Usage
    * least one DML 
    * change db state
    * use within one db
        
    * atomicity 原子 - management
        - work is atomic (all done or fail)
    * consistency 一致 - 
        - data is integrity and consist 
        - structure is correct
    * isolation 隔离 - isolation
        - isolated
    * durability 持续 -  loging 
        - change is permanently 
- Why use

- Why not use


### **Concurrency**
    pessimistic control when lock cost less

    optimistic control when roll back cost less

### **Isolation level**
    * read uncommited - can read while modify (dirty read)
    * read commited - can't read while modify but can change by others (nonrepeatable read)
    * repeatable read - can't read update, but can insert (phantom data)
    * serializable 
    * snapshot
        - maintained in tempdb
        - optimistic

### **Deadlock**
    multiple process simultaneously require locks held by other

    fix : examine deak lock trans and kill the simple one with an error to break dead lock


### **Reduce deadlock**
    * trans access table in same order (守秩序)
    * hold lock when repeatable read are necessary (别人要重复读就等)
    * avoid long run transactions (不要花太长时间)
    * avoid user input while hold lock (占位置之后不要干别的)
    * avoid numerous simultaneous execution of DML (不要同时大量做增删改)

### **Store Procedure** 
    groups one or more sql statement into logical unit, store as an object
    
    when executed for first time, sql will store most optimal query plan in memory cache for reuse

- Syntax

    ```sql
    create procedure [name] 
    (
        @var1 type,
        @var2 int = value,
        @var3 int OUTPUT
    )
    as 
    if
    begin

    select....
    return(1)
    

    end
    else
    begin
    @var3 = ..
    return(@var2)
    end
    go
    ```

- Example
    
    ```sql

    ```
- Usage
    * call procedure - exec name @var = , @var2 = @read output / exec name var1, var2, @var3 output
    * set automatically exec

- Why use
    * faster and reliable performance
    * security for injection 
    * centralize sql code easy debug
    * reduce network traffic
    * code reuseability

- Why not use

### **Function**
    built-in function
    user-defined functions
        a common language runtime(CLR) routine that accepts parameters perform action
     

- Syntax
    ```sql
    create function name 
    (
        id type
    )
    returns int
    AS
    begin

    end
    GO

    select name(id) 
    ```

- Example
    ```sql
    CREATE FUNCTION dbo.ISOweek (@DATE datetime)  
    RETURNS int  
    WITH EXECUTE AS CALLER  
    AS  
    BEGIN  
        DECLARE @ISOweek int;  
        SET @ISOweek= DATEPART(wk,@DATE)+1  
            -DATEPART(wk,CAST(DATEPART(yy,@DATE) as CHAR(4))+'0104');  
    --Special cases: Jan 1-3 may belong to the previous year  
        IF (@ISOweek=0)   
            SET @ISOweek=dbo.ISOweek(CAST(DATEPART(yy,@DATE)-1   
                AS CHAR(4))+'12'+ CAST(24+DATEPART(DAY,@DATE) AS CHAR(2)))+1;  
    --Special case: Dec 29-31 may belong to the next year  
        IF ((DATEPART(mm,@DATE)=12) AND   
            ((DATEPART(dd,@DATE)-DATEPART(dw,@DATE))>= 28))  
            SET @ISOweek=1;  
        RETURN(@ISOweek);  
    END;  
    GO  
    SET DATEFIRST 1;  
    SELECT dbo.ISOweek(CONVERT(DATETIME,'12/26/2004',101)) AS 'ISO Week'; 
    ```
- Usage
    * only used in sql statement, most in select or present data 

- Why use

- Why not use

### **Trigger**
    specical type store procedure that executed when user issue DML (not select)
    * DML trigger
    * DDL trigger
    * Logon trigger
    * server level
- Syntax
    ```sql
    create trigger tri_name
    on (table|view)
    (for = after | instead of)
    (insert|update|delete)
    as
    {
        sql....
    }
    ```

- Example
    
    DML
    ```sql
    create trigger tri
    on department
    for insert as
    begin
        ...
    end
    ```
    DDL
    ```sql
    CREATE TRIGGER Drop Trigger 
    ON DATABASE
    FOR DROP_TABLE, ALTER_TABLE
    AS
    PRINT ‘Trigger is fired to rollback!’
    ROLLBACK
    ```
- Usage
    * automatically fired on a event
    * cannot explicitly executed 

    insert trigger

    delete trigger
    * effects
        * delete - parent delete all children also delete
        * restrict - child exist can not delete
        * net null - set child to null
    update trigger
    * effects
        * update - change parent change child
        * restrict - child exists can not change parents

- Why use
    * enforce integrity 加强完整性
    * maintain audit record 审计记录
    * implement business rule 实施特殊规则
    * cascading update 级联更新
- Why not use


### OUTPUT
    - for DML 
    - RETURN rows as part of DML
    - access to INSERTED and DELETED system table
    输出来看

```sql
UPDATE Employee 
SET Salary = Salary * 1.10
OUTPUT 
DELETED.* AS [Old Values], 
INSERTED.* AS New Values 

DECLARE @TempTable TABLE (EMPID INT)

INSERT Employee 

OUTPUT INSERTED.EMPID 
INTO @TempTable 

VALUES ('David')

INSERT Employee 

OUTPUT INSERTED.EMPID 
INTO @TempTable 

VALUES ('James')
SELECT * FROM @TempTable
```
### **Cursor**
    object applied on result set to read and load the result row by row
    
- Syntax
    ```sql
    
    ```

- Example
    
    ```sql
    declare <name> cursor for
    select eid from emp where ...

    open <name>
    fetch next from <name> into @var

    while @@fetch_status = 0
    Begin
        insert into table(col) values (@var)

        fetch next from <name> into @var
    End
    ```
- Usage

- Why use
    * used for data migration
- Why not use
    * performance killer

### **Index** 
    objects allows sql server to find data in a table without scanning entire table
    

- Syntax
    ```sql
    create index ind_name on table (col)
    ```

- Example
    
    ```sql
    CREATE CLUSTERED INDEX i1 
    ON d1.s1.t1 (col1)

    CREATE UNIQUE INDEX i1 
    ON t1 (col1 DESC, col2 ASC, col3 DESC); 

    create nonclustered index
    ```
- Usage
    - clustered index (only one, sorted, point to physical, default primary)
    - non clustered index (249, not sorted, point to clustered, no cluster to physical)

- Why use
    * quick find data in where 
    * matching in join
    * maintain uniqueness in insert update
    * sort group 
    * separate structure to the table


- Why not use
    * take disk space
    * insert/ delete/ update will be slow
    * cluster index cover query ??


### Overall


### **Temporary table VS temporary variables**

    temp var limitation
    temp variable can not use as input or output
    temp var will not exist after sp, no table to drop
    can not create nonclustered index unless index is side effect of pk????
| Temp table   | Temp variable   |
| -------- | -----  |
| create + insert/select into | declare + insert/select |
| scope in session | scope in batch or store procedure|
| drop temp table | can not use drop |
| support most constraint | don't support fk |
| support rollback | do not support rollback ??|

both in tempdb


### **Difference CTE AND VIEW**

| CTE   | VIEW |
| -------- | -----  |
| temporary view not store | physical object present in db, no physical data, only schema  |
| scope in next quert | scope  long |
| USE with | USE create |
| call itself, recursive| can not call itself |
| no index | can have index |

### **Difference store procedure and function**
| Store procedure |  Function |
|-----|-----|
| optional return | must return value|
| both input or ouput para | only input para |
| can call function | can not call procedure |
| allow DML | only select |
| procedure can not use in select/where/having | embeded in select/where/having |


### **difference Join and Union**
Union is operating on the result sets – combine multiple queries into a single query with all the records of queries

Join is to join two table base on foreign keys before filter operation – combine data form multiple queries with the column 

### **difference view and store procedure**
Store procedure accept parameters , view not

Store procedure can not be used as building large query, view can

Store procedure can have several statements, loops, view can only have select

Store procedure can not be used as target of DML, view can 

View has just select statements but storeprocedure has collection of DML and DDL statements.

### **difference trigger and store procedure**
Triggers happen on DML statements occurence where as store procs should be excuted manually.

we can excute procedure whenever we want, trigger can only execute when event is fired

we can call SP in another SP, but we can’t call trigger within trigger

Sp can take input parameters, trigger can not

Sp can return value, trigger can not

### begin end , go
begin end enclousre a group of statement

go open new batch

### **Delete all duplicate row in table**
```sql
WITH CTE AS(
   SELECT [col1], [col2], [col3], [col4], [col5], [col6], [col7],
       RN = ROW_NUMBER()OVER(PARTITION BY col1 ORDER BY col1)
   FROM dbo.Table1
)
DELETE FROM CTE WHERE RN > 1

DELETE
FROM FriendsData 
WHERE fID NOT IN
(
SELECT MIN(fID)
FROM FriendsData 
GROUP BY UserID, FriendsID)
``` 
