# peakperformance
# Project Name  :   Peak Performance

![Kiku](images/Kiku.jpg)

Peak Performance is a powerful solution that delivers numerous benefits to Snowflake customers. It facilitates maximum adoption growth and data maturity, ensuring complete enterprise visibility across the health, cost, and performance of their Snowflake Data Cloud. By leveraging Peak Performance, organizations can gain immediate data intelligence across their entire enterprise data estate. This enables visibility across every connected data source and database, allowing businesses to analyze patterns, optimize operations, and data-driven business growth. With this enhanced visibility, organizations can optimize their investment in Snowflake and extract the maximum value from their data.

•	Get Started Today:
Unlock your Snowflake Data Cloud's full potential and transform how your organization manages, analyzes, and optimizes data with Peak Performance. Our comprehensive solution empowers businesses with unmatched visibility and intelligence across their entire data landscape, ensuring efficient data management, governance, and enhanced decision-making capabilities.


## Table of Contents

- [Installation](##installation)
- [Usage](##usage)


## Installation

•	Navigate to Data Products --> Market Place
    Search for Peak Performance  --> Click On "Get"

## Usage

•	Comprehensive Data Intelligence: 
        With Peak Performance, you can instantly gain visibility across all connected data sources and databases within your enterprise. 
•	Enterprise Visibility: 
        With Peak Performance, you can monitor the health, cost, and performance of your Snowflake Data Cloud. This means you can always stay on top of your data operations and make informed decisions.
•	Optimized Cost Performance Analysis: 
        Peak Performance provides detailed insights into your data estate and Snowflake usage. It enables businesses to identify areas of inefficiency and optimize credit consumption, storage, and query efficiencies. This leads to higher ROI and a supercharged Snowflake environment, ensuring you maximize your Snowflake investment.
•	User and Query Analytics: 
        With Peak Performance, you can track successful and failed logins, average execution time by user or query type, and much more for enhanced security and efficiency. 
•	Optimizing Data Operations: 
        With Peak Performance, you can access detailed analytics on CPU usage, execution times, and query performance to fine-tune your data operations.

## SETUP SQL
Setup references to objects related to  Alation Consumption Tracker  START

```sql


SET dbname = 'ALATIONACTAA';
SET schemaAct = 'ACT';

SET appSchema = 'USE SCHEMA CODE_SCHEMA';
EXECUTE IMMEDIATE $appSchema;
 
--###############   Setup references to objects related to  Alation Consumption Tracker  START   ###############--
SET tbl = 'QLI_EVENTS';
CALL UPDATE_REFERENCE(
$tbl , 'ADD', SYSTEM$REFERENCE('TABLE', $dbname || '.' || $schemaAct || '.' || $tbl, 'PERSISTENT', 'SELECT'));

SET tbl = 'FLAGS';
CALL UPDATE_REFERENCE(
$tbl , 'ADD', SYSTEM$REFERENCE('TABLE', $dbname || '.' || $schemaAct || '.' || $tbl, 'PERSISTENT', 'SELECT'));

SET tbl = 'RDBMS_DATASOURCES';
CALL UPDATE_REFERENCE(
    $tbl , 'ADD', SYSTEM$REFERENCE('TABLE', $dbname || '.' || $schemaAct || '.' || $tbl, 'PERSISTENT', 'SELECT'));

SET tbl = 'RDBMS_TABLES';
CALL UPDATE_REFERENCE(
    $tbl , 'ADD', SYSTEM$REFERENCE('TABLE', $dbname || '.' || $schemaAct || '.' || $tbl, 'PERSISTENT', 'SELECT'));

SET tbl = 'EVENT_TABLE_MAPPING';
CALL UPDATE_REFERENCE(
    $tbl , 'ADD', SYSTEM$REFERENCE('TABLE', $dbname || '.' || $schemaAct || '.' || $tbl, 'PERSISTENT', 'SELECT'));

SET tbl = 'QLIEVENTSVIEW';
CALL UPDATE_REFERENCE(
    'QLIEVENTSVIEW' , 'ADD', SYSTEM$REFERENCE('VIEW', $dbname || '.' || $schemaAct || '.' || $tbl, 'PERSISTENT', 'SELECT'));

--###############   Setup references to objects related to  Alation Consumption Tracker  END   ###############--
```

Setup references to objects related to Alation Analytics  START

```sql
--###############        Setup references to objects related to Alation Analytics  START       ###############--

SET appName = 'PEAKPERFORMANCE';
SET dbname = 'ALATIONACTAA';
SET appSchema = 'USE SCHEMA CODE_SCHEMA';
EXECUTE IMMEDIATE $appSchema;

SET schemaAA = 'ANALYTICS';

SET tbl = 'RDBMS_DATASOURCES';
CALL UPDATE_REFERENCE(
'AA_RDBMS_DATASOURCES' , 'ADD', SYSTEM$REFERENCE('TABLE', $dbname || '.' || $schemaAA || '.' || $tbl, 'PERSISTENT', 'SELECT'));
  
SET tbl = 'RDBMS_TABLES';
CALL UPDATE_REFERENCE(
'AA_RDBMS_TABLES' , 'ADD', SYSTEM$REFERENCE('TABLE', $dbname || '.' || $schemaAA || '.' || $tbl, 'PERSISTENT', 'SELECT'));
  
SET tbl = 'ALATION_GROUP';
CALL UPDATE_REFERENCE(
$tbl , 'ADD', SYSTEM$REFERENCE('TABLE', $dbname || '.' || $schemaAA || '.' || $tbl, 'PERSISTENT', 'SELECT'));
  
SET tbl = 'ALATION_SET_MEMBER';
CALL UPDATE_REFERENCE(
$tbl , 'ADD', SYSTEM$REFERENCE('TABLE', $dbname || '.' || $schemaAA || '.' || $tbl, 'PERSISTENT', 'SELECT'));
  
SET tbl = 'ARTICLE';
CALL UPDATE_REFERENCE(
$tbl , 'ADD', SYSTEM$REFERENCE('TABLE', $dbname || '.' || $schemaAA || '.' || $tbl, 'PERSISTENT', 'SELECT'));
  
SET tbl = 'CATALOG_SET_MEMBERSHIP';
CALL UPDATE_REFERENCE(
$tbl , 'ADD', SYSTEM$REFERENCE('TABLE', $dbname || '.' || $schemaAA || '.' || $tbl, 'PERSISTENT', 'SELECT'));
  
SET tbl = 'CONVERSATION';
CALL UPDATE_REFERENCE(
$tbl , 'ADD', SYSTEM$REFERENCE('TABLE', $dbname || '.' || $schemaAA || '.' || $tbl, 'PERSISTENT', 'SELECT'));
  
SET tbl = 'CURATION_HISTORY';
CALL UPDATE_REFERENCE(
$tbl , 'ADD', SYSTEM$REFERENCE('TABLE', $dbname || '.' || $schemaAA || '.' || $tbl, 'PERSISTENT', 'SELECT'));
  
SET tbl = 'CUSTOM_GLOSSARY';
CALL UPDATE_REFERENCE(
$tbl , 'ADD', SYSTEM$REFERENCE('TABLE', $dbname || '.' || $schemaAA || '.' || $tbl, 'PERSISTENT', 'SELECT'));

SET tbl = 'EXECUTION_EVENT';
CALL UPDATE_REFERENCE(
$tbl , 'ADD', SYSTEM$REFERENCE('TABLE', $dbname || '.' || $schemaAA || '.' || $tbl, 'PERSISTENT', 'SELECT'));

SET tbl = 'QUERY';
CALL UPDATE_REFERENCE(
$tbl , 'ADD', SYSTEM$REFERENCE('TABLE', $dbname || '.' || $schemaAA || '.' || $tbl, 'PERSISTENT', 'SELECT'));
  
SET tbl = 'RDBMS_COLUMNS';
CALL UPDATE_REFERENCE(
$tbl , 'ADD', SYSTEM$REFERENCE('TABLE', $dbname || '.' || $schemaAA || '.' || $tbl, 'PERSISTENT', 'SELECT'));
  
SET tbl = 'RDBMS_SCHEMAS';
CALL UPDATE_REFERENCE(
$tbl , 'ADD', SYSTEM$REFERENCE('TABLE', $dbname || '.' || $schemaAA || '.' || $tbl, 'PERSISTENT', 'SELECT'));
  
SET tbl = 'SEARCH_CLICKS';
CALL UPDATE_REFERENCE(
$tbl , 'ADD', SYSTEM$REFERENCE('TABLE', $dbname || '.' || $schemaAA || '.' || $tbl, 'PERSISTENT', 'SELECT'));
  
SET tbl = 'SEARCH_QUERIES';
CALL UPDATE_REFERENCE(
$tbl , 'ADD', SYSTEM$REFERENCE('TABLE', $dbname || '.' || $schemaAA || '.' || $tbl, 'PERSISTENT', 'SELECT'));
  
SET tbl = 'STEWARDS';
CALL UPDATE_REFERENCE(
$tbl , 'ADD', SYSTEM$REFERENCE('TABLE', $dbname || '.' || $schemaAA || '.' || $tbl, 'PERSISTENT', 'SELECT'));
  
SET tbl = 'USERS';
CALL UPDATE_REFERENCE(
$tbl , 'ADD', SYSTEM$REFERENCE('TABLE', $dbname || '.' || $schemaAA || '.' || $tbl, 'PERSISTENT', 'SELECT'));
  
SET tbl = 'USER_GROUP_MEMBERSHIP';
CALL UPDATE_REFERENCE(
$tbl , 'ADD', SYSTEM$REFERENCE('TABLE', $dbname || '.' || $schemaAA || '.' || $tbl, 'PERSISTENT', 'SELECT'));
  
SET tbl = 'VISITS';
CALL UPDATE_REFERENCE(
$tbl , 'ADD', SYSTEM$REFERENCE('TABLE', $dbname || '.' || $schemaAA || '.' || $tbl, 'PERSISTENT', 'SELECT'));


--###############         Setup references to objects related to Alation Analytics  END        ###############--
```

Setup references to objects related to Alation Analytics  START

```sql
SHOW REFERENCES IN APPLICATION Peak_Performance_Lite;
```


### This repository contains the sample code for the [Getting Started with Snowflake Native Apps Quicsktart](https://quickstarts.snowflake.com/guide/getting_started_with_native_apps/).

![Snowflake Native Apps](https://quickstarts.snowflake.com/guide/getting_started_with_native_apps/img/edcfa4000a03ae36.png)
