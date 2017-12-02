# Web App #

## Web Application ##

* HTTP protocal is the heat
* client/server architecture
* client side host by browser takes the form of HTML pages
* server side runs under Web Server (IIS)

### Static WebPages && Dynamic WebPages ###

Static page will not change when being sent to browser

Dynamic WebPages has ability to perform processing on data that is being sent to the client

## Asp.NET ##

is a serve side technology in .net, building dynamic webpages

* caching support
* easy developement
* Configuration
* reliability
* event base

    asp.NET /asp.NET /HTTP handle
    HTTP Module -> global.asax
    asp.NET Runtime
    Host IIS

### Web Form ###

* asp page
  * aspx UI design
    * @page attributes
  * aspx.cs code file

Server Control

* Built-functionality
* Common Object Model
* Create browser specific HTML

Html server Control

### Web Control ###

System.Web.UI.Control

* DataGrid
* DropDownList

Input Validation before Web Application Processed

* Reuqired Field
* Compare Validator
* Range Validator

## Info ##

default port 53165

## ADO.NET ##

ADO.NET is use to connect Web application to data source

System.Data
  Important Object
  DbConnection - Establish a connection to a data source
  DbCommand - Executes a command against a data source
  DataReader - Reads a forward-only read-only stream
  DataAdapter - populate a DataSet and resolves update with the data source

### two models for data access/ ado.net approaches models ###

Connection-oriented || Connectionless

connected approach  ||  disconnected approach

connectless - connection opening and closing are managed by the framework automatically

* No permanent connection short connections - DataAdapter
* Data cached in main memory
* changes in main memory may be in conflict with changes in data source
* good for many parallel and long lasting access operation

Connection-oriented - need manually control connection /need connection open and close manually 

* keeps the connection to data base
* always up-to-date
* good for short running transaction and a few parallel access operation

步骤 procedure in connection oriented

1. Find the connection string of the database
1. open the connection
1. write a command
1. connect to the command with connection
1. execute the command
1. close the connection

Connection Strings

### DataReader vs DataAdapter ###

DataReader

* Forward only, read only
* Fast access to data
* Connected to a data source
* bind to one control only
* Manage the connection yourself
* Manage the data yourself or bind to list-bound control
* use fewer server resources

DataAdapter - DataSet

* Dataset
  * objects allow you to store tables of data
  * collection of tables with collection of datarelation
  * tables consists of column
  * use dataAdapter to load data from data source

* can read and write/ forward and backward
* slow access
* include multiple tables
* can disconnected
* bind to multiple controls
* support VS .net tools

## State Manage ##

* state is ability to retain user information in web application
* state management is process you maintain the sane info though request for same or different Web pages

Client Management

    Cookies
    ViewState
    Query String
    Hidden Fields

Server Side
    Sessions
    Application[] variable
    Database
    Cache

### Transfer Data ###

Between Pages

* using HyperLink()
* using Request - Response.Redirect(“Page2.aspx?UserId={0}",strUserID)
* using Session[]
* using Cookie (small amount data and security problem)

In page and bwetween function

* ViewState[]

## Linq ##

Stands for Language Integrated Query

write queries against in-memory collections and other resource

* Query Syntax
* Method Syntax

Linq replace Foreach (execute in foreach statement)

## Entity FrameWork ##

Is an Object/Reational Mapping Framework that enables developers to work with relational data

O/RM is a tool for storing data from domain objects to relational database,
allows to keep database design separate from out domain class design

* domain class objects
* relational database objects
* mapping info on how objects map to relational database objects(tables, views & storedprocedure)

ORM provide function

* create object model by database schema - DB first model
* create database schema by object model - code first model
* Query data by oo API
* data mantipulation operations

EDM Model

    Conceptual Model => Mapping => Storage Model

DBContext is an important part of entity framework. it is a bridge between domain or entity class and database

Type of Entity in framework - dynamic proxy(poco entity)

Entity Property Types

* scalar properties - actual value contained in entity
* navigation properties - pointers to other related entities

Entity State

* added
* unchanged
* modified
* deleted

### lazy loading and eager loading ###

loading related entities of an entity

Lazy loading: (delay loading of related data until request it)

* related objects are not loaded automatically with its parent object until they are request
* child entity is populated when it is requested
* set context.ContextOptions.LazyLoadingEnabled = false;

Eager loading:

* related objects are loaded automatically with its parents object
* use include

### delay/deferred execution and early/Immediate execution ###

for linq queries, there are two different behaviours of execution

Deferred Execution:

* query is not executed when it is declared
* it is executed when query variable is iterated over not when it is created
* get most updated data, execute frequently
* improve performance when you have mantipulate latge data collections
* Collection result have smaller memory foot prints

Immediated Execution:

* caching query results
* return a singleton value and executed immediately 
* using count() average() max() toList()(conversion operator which allow you to make a copy/snapshot of the result, and access without need to reexecute the query)

### Ways to Connected to DB using ADO ###

Repository is a class with data access methods

* using Conenction Model (ConnectionString, Entity class(table) Repository class(Connection and sql command))
* using Linq (create dbml file connect to db (linq to sql class) and use NameContext Object)
* using Entity FrameWork Data model (download the package for the framework)(edmx)

## WCF - windows communication foundation ##

