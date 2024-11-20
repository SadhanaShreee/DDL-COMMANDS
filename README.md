# DDL-COMMANDS

## AIM:
 To study and implement DDL commands and different types of constraints.
 ## THEORY:
 ```
 1.CREATE:
 This is used to create a new relation (table)
 Syntax:
 CREATETABLE(field_1 data_type(size),field_2 data_type(size), .. . );
 2.ALTER:
 This is used to add some extra fields into existing relation.
 Syntax:
 ALTERTABLErelation_name ADD(new field_1 data_type(size) );
 (a)ALTERTABLE...ADD...:
 ALTERTABLEstdADD(AddressCHAR(10));
 (b )ALTERTABLE...MODIFY...:
 ALTERTABLErelation_nameMODIFY(field_1 newdata_type(Size)
 ( c) ALTERTABLE..DROP....
 ALTERTABLErelation_nameDROPCOLUMN(field_name);
 (d)ALTERTABLE..RENAME...:
 ALTERTABLErelation_name RENAMECOLUMN(OLDfield_name) to(NEW field_name);
 3.DROP TABLE:
 This is used to delete the structure of a relation. It permanently deletes the records in the table.
 Syntax:
 DROPTABLErelation_name;
4.RENAME:
 It is used to modify the name of the existing database object.
 Syntax:
 RENAMETABLEold_relation_nameTOnew_relation_name;
 CONSTRAINTS:
 Constraints are used to specify rules for the data in a table. If there is any violation between the
 constraint and the data action, the action is aborted by the constraint. It can be specified when the table is
 created (using CREATE TABLE statement) or after the table is created (using ALTER TABLE statement).

 1.NOT NULL: When a column is defined as NOTNULL, then that column becomes a mandatory
 column. It implies that a value must be entered into the column if the record is to be accepted for storage in
 the table.
 Syntax:
 CREATETABLETable_Name(column_namedata_type (size) NOT NULL, );
 2.UNIQUE: The purpose of a unique key is to ensure that information in the column(s) is unique
 i.e. a value entered in column(s) defined in the unique constraint must not be repeated across the column(s).
 Atable may have many unique keys.
 Syntax:
 CREATETABLETable_Name(column_namedata_type(size)UNIQUE,….);
 3.CHECK:Specifies a condition that each row in the table must satisfy. To satisfy the constraint, each
 row in the table must make the condition either TRUE or unknown (due to a null).
 Syntax:
 CREATE TABLE Table_Name(column_name data_type(size) CHECK(logical
 expression), ….);
 4.PRIMARY KEY: A field which is used to identify a record uniquely. A column or combination
 of columns can be created as primary key, which can be used as a reference from other tables. A table
 contains primary key is known as Master Table.

 ● Itmust uniquely identify each record in a table.
 ● Itmust contain unique values.
 ● Itcannot be a null field.
 ● Itcannot be a multi port field.
 ● Itshould contain a minimum number of fields necessary to be called unique.
Syntax:
 CREATETABLE Table_Name(column_name data_type(size) PRIMARY KEY, ….);
 5.FOREIGN KEY: It is a table level constraint. We cannot add this at column level. To reference any
 primary key column from other table this constraint can be used. The table in which the foreign key is
 defined is called a detail table. The table that defines the primary key and is referenced by the foreign key
 is called the master table.
 Syntax:
 CREATE TABLETable_Name(column_namedata_type(size)FOREIGN KEY(column_name)
 REFERENCEStable_name);
 6.DEFAULT : The DEFAULT constraint is used to insert a default value into a column. The
 default value will be added to all new records, if no other value is specified.
 Syntax:
 CREATETABLE Table_Name(col_name1,col_name2,col_name3 DEFAULT ‘’);
```
```
## Question 1:
 Write a SQL Query for Creating a table name as "Employee" with the following attributes
 eid as primarykey with autoincrement
 name as varchar(50)
 designation as varchar(30)
 
 Answer:
 CREATETABLE Employee(
 eid INTEGER PRIMARYKEY AUTOINCREMENT,
 name VARCHAR(50),
 designation VARCHAR(30));

 ## Output:
 ![Screenshot 2024-11-20 133220](https://github.com/user-attachments/assets/5ace40aa-eb89-49cf-b37e-63c5d5425955)

 ## Question 2:
  Consider a situation already created a table "customer" from that create a new table
 "customerbackup" with all the attributes available in the table "customer"
 Create a table name as "customerbackup" with all the attributes available in the table "customer"
 
 Answer:
 CREATETABLE customerbackup AS
 SELECT *FROMcustomer;

 ## Output:
 
 ## Question 3:
  Write a SQL Query for creating a table "Students" which already exists so use proper keyword in
 order to avoid error message
 Create a table name as "Students" with the following attributes ,use default keyword in the
 attribute year as 2
 id as number
 grade as varchar(50)
 year as integer
 
 Answer:
 CREATETABLE IF NOTEXISTSStudents(
 id number,
 grade varchar(50),
 year integer);

 ## Output:
 ![Screenshot 2024-11-20 133429](https://github.com/user-attachments/assets/d5790515-9e3e-4ea5-93ed-f212b3ec0ace)

 ## Question 4:
 Create a table name as "Employee" with the following attributes
 eid as primarykey with autoincrement
 name as varchar(50)
 designation as varchar(30)
 dob as date
 doj as date
 
 Answer:
 CREATETABLE Employee(
 eid INTEGER PRIMARYKEY AUTOINCREMENT,
 name VARCHAR(50),
 designation VARCHAR(50),
 dob DATE,
 doj DATE,
 );

 ## Output:
 ![Screenshot 2024-11-20 133516](https://github.com/user-attachments/assets/54cae8a2-9374-41a5-ad54-080b2e08a065)

 ## Question 5:
 Write a SQL query to Add a new column mobilenumber as number in the Student_details table.
 
 Answer:
 ALTERTABLEStudent_details
 ADDmobilenumber number;

 ## Output:
 ![Screenshot 2024-11-20 133609](https://github.com/user-attachments/assets/ef710e33-fce7-4490-b2e6-25855eb4abd8)

 ##  Question 6:
 Write a SQL query to Add a new ParentsNumber column as number and Adhar_Number as
 Number in the Student_details table.
 
 Answer:
 ALTERTABLEStudent_details
 ADDParentsNumber number;
 ALTERTABLEStudent_details
 ADDAdhar_Number number;

 ## Output:
 ![Screenshot 2024-11-20 133653](https://github.com/user-attachments/assets/71108f3d-a808-4bac-b005-d336454f9a05)

 ## Question 7:
 Write a SQL query to Add a new column Mobilenumber as number in the Student_details table.
 
 Answer:
 ALTERTABLEStudent_details
 ADDMobilenumber number;

 ## Output:
 ![Screenshot 2024-11-20 133653](https://github.com/user-attachments/assets/5c6962cb-8d74-4cbe-9003-3bb61bd386cf)

 ## Question 8:
 Write a SQL Query for inserting records with subquery
 Consider two tables, SourceTable and DestinationTable, where SourceTable contains information about
 individuals' ID, Name, and Age. Assume you want to insert records into DestinationTable from SourceTable
 where the Name is Kumar. Provide the SQL query for achieving this insertion using a subquery.
 
 Answer:
 INSERT INTO DestinationTable
 SELECT *FROMSourceTable
 WHEREName=='Kumar'

 ## Output:
 ![Screenshot 2024-11-20 133949](https://github.com/user-attachments/assets/561a26dd-f5d1-40b4-b545-42f4efdc1db3)

## Question 9:
 Write a SQL Query for inserting the below values as multiple row format in the table "Student"
 Note: In the Student Table attribute year set as default 3
 Sample Table:" Student"
 
 Answer:
 INSERT INTO Student
 VALUES(3,'Jeni','Female','English',96,3);
 INSERT INTO Student
 VALUES(4,'Bob Johnson','Male','History',90,3);
 INSERT INTO Student
 VALUES(5,'Sharvesh','Male','Botany',97,3);
 INSERT INTO Student
 VALUES(6,'Mathew','Male','Science',85,3);

## Output:
![Screenshot 2024-11-20 134055](https://github.com/user-attachments/assets/f2066616-eb98-4976-96cb-b139c52c1342)

## Question 10:
 Write a SQL query for inserting new customer details (customer_id, name, email) from the 'old_customers'
 table into the 'new_customers' table with the subquery. Ensure that only customer email as "---@gmail.com"are
 included in the transfer.
 
 Answer:
 INSERT INTO new_customers (customer_id,name,email)
 SELECT customer_id , name,email
 FROMold_customers
 WHEREemail LIKE ‘%@gmail.com’

 ## Output:
 ![Screenshot 2024-11-20 134142](https://github.com/user-attachments/assets/71ae72e6-edc8-46d8-94b1-1f02158a6d41)
```

 ## Result:
 Thus , the SQL queries to implement different types of constraints and DDL commands have been executed
 successfully



