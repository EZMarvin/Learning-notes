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

### ado.net approaches models ###

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

### lazy loading and eager loading ###

loading related entities of an entity

Lazy loading:

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

Immediated Execution:

* caching query results
* return a singleton value and executed immediately 
* using count() average() max() toList()(conversion operator which allow you to make a copy/snapshot of the result, and access without need to reexecute the query)