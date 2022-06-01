# **User-Defined Functions**
## **Introduction** 
In the Server Query Language (SQL), a User-Defined Function is an object that allows for scripts to be “stored in the database [to] avoid writing the same code over and over again” ([SQL Shack](https://www.sqlshack.com/learn-sql-user-defined-functions/), 2020) (External Site). It enables a user to control the input parameters and how it is defined to reach the desired output. The three types of User-Defined Functions are Scalar, Inline, and Multi-Statement Functions which can contain an increasing complexity of statements to yield a singular or unique set of values. The syntax for the object depends on whether the Create, Alter or Drop is used and can encapsulate SQL statement instructions that are either small or bulky (Figure 1). Thus, it is beneficial in situations where the function can be recalled for “calculation you’ll repeat throughout your database” ([SQL Shack](https://www.sqlshack.com/learn-sql-user-defined-functions/), 2020) (External Site).

![image](https://user-images.githubusercontent.com/105769165/171306405-4025e393-9440-4ee1-b751-e2fe74bd6573.png)
###### Figure 1: Create/Alter/Drop Syntax for User-Defined Function

## **Scalar, Inline and Multi-Statement Functions**
A User-Defined Scalar Function takes any number of parameters and “returns a single value each time it is invoked” (IBM, https://www.ibm.com/docs/en/db2-for-zos/11?topic=function-sql-Scalar-functions, 2022) (External Site). Much like the other User-Defined Functions, it is used to simplify code when complex and bulky calculations appear in many queries. The syntax encapsulates SQL statements designed to output a singular value by the defined function (Figure 2). As an example, the UCASE Scalar Function returns each column value per row in uppercase (Figure 3). As such, it operates on each record independently and is based on user input to return a single value. 

![image](https://user-images.githubusercontent.com/105769165/171306539-96d0ddd6-86dd-4ac7-8210-a20f09c317af.png)
###### Figure 2: Scalar Function Syntax
![image](https://user-images.githubusercontent.com/105769165/171306570-13fcafc9-f54d-4caa-8552-8d2979338498.png)
###### Figure 3: UCASE() Scalar Function

A User-Defined Inline Function “is a table expression that can accept parameters, perform an action and provide as its return value, a table” (SQL Server Central, https://www.sqlservercentral.com/articles/creating-and-using-Inline-table-valued-functions, 2020) (External Site). It is a table-valued function that encapsulates the code in a single executable database object allowing the user-defined object to be reused many times. It is much like a View but with the ability to accept parameters. The syntax involves a user-defined variable followed by the parameter and data type. It is then returned as a table displaying the output as defined by the return statements (Figure 4). As an example, the ‘Sales.fn_OderDetails_IF” User-Defined Inline Function takes on the @SalesOrderID parameter values and returns it as a table based on the select statement definition (Figure 5). Thus, it is a great way to detail current table data and present them in varying ways for informational view.     

![image](https://user-images.githubusercontent.com/105769165/171306630-41bf9ba8-caa8-4cee-8cc9-5f3fd41ad037.png)
###### Figure 4: Inline Function Syntax
![image](https://user-images.githubusercontent.com/105769165/171306657-1488becf-910f-47af-bef2-93637ab23f66.png)
###### Figure 5: Inline Function Example

Lastly, a User-Defined Multi-Statement Function much like an Inline Function would return a table type result set, but with the difference in that the table is explicitly constructed in the script. The syntax involves defining the table structure to be returned followed by the function body encapsulated by a Begin and End (Figure 5). Here, the Name and DateOrdered columns are created and will be returned by the getCustomerAndDate() function, where the columns are defined by the encapsulated select statement within the Begin-End Statements (Figure 5). Therefore, this allows the user to process unique and focused business logic by constructing a virtual table on the fly. 

![image](https://user-images.githubusercontent.com/105769165/171306733-41bf8aa7-5bd7-4ea2-812e-f76ca382eb5f.png)
###### Figure 6: Multi-Statement Function Syntax and Sample

## **Summary**
The goal is not to repeat yourself, which would otherwise make your SQL code bulky and hard to read. User-Defined Functions give the ability to encapsulate these SQL scripts, allowing for recall whenever desired informational value needs to be transformed by these objects. Depending if a single or tabular value is desired, Scalar, Inline, and Multi-Statement Functions are tools that can reduce repetitions and increase performance of the SQL code generated. 
