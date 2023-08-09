Only first 3 normal forms are generally followed
## The normal forms of a database are as follows:

1. First Normal Form (1NF): This form ensures that each column in a table contains only atomic values, meaning that each value in a column is indivisible.

Example:
Consider a table called "Students" with the following columns:
- StudentID (Primary Key)
- Name
- Address
- Phone Numbers (stored as a comma-separated list)

To convert this table to 1NF, we need to remove the multi-valued attribute "Phone Numbers" and create a separate table called "PhoneNumbers" with the columns:
- StudentID (Foreign Key)
- Phone Number

2. Second Normal Form (2NF): This form builds upon 1NF and requires that all non-key attributes in a table are fully dependent on the primary key. In other words, there should be no partial dependencies.

Example:
Consider a table called "Orders" with the following columns:
- OrderID (Primary Key)
- ProductID (Primary Key)
- Quantity
- Price

To convert this table to 2NF, we need to remove the partial dependency of "Quantity" on the composite primary key (OrderID, ProductID). We can create a separate table called "OrderDetails" with the columns:
- OrderID (Foreign Key)
- ProductID (Foreign Key)
- Quantity

3. Third Normal Form (3NF): This form further refines the database design by eliminating transitive dependencies. It ensures that no non-key attribute is dependent on another non-key attribute.

Example:
Consider a table called "Employees" with the following columns:
- EmployeeID (Primary Key)
- DepartmentID (Foreign Key)
- DepartmentName
- ManagerID (Foreign Key)
- ManagerName

To convert this table to 3NF, we need to remove the transitive dependency of "ManagerName" on "DepartmentName". We can create a separate table called "Departments" with the columns:
- DepartmentID (Primary Key)
- DepartmentName

4. Boyce-Codd Normal Form (BCNF): This form is an extension of 3NF and deals with additional dependencies that may exist in a table. It requires that every determinant in a table is a candidate key.

Example:
Consider a table called "Students" with the following columns:
- StudentID (Primary Key)
- CourseID (Primary Key)
- CourseName
- InstructorID (Primary Key)
- InstructorName

To convert this table to BCNF, we need to remove the dependency of "InstructorName" on "CourseName". We can create a separate table called "Courses" with the columns:
- CourseID (Primary Key)
- CourseName

5. Fourth Normal Form (4NF): This form addresses multi-valued dependencies and ensures that there are no non-trivial multi-valued dependencies between attributes.

Example:
Consider a table called "Employees" with the following columns:
- EmployeeID (Primary Key)
- Skills (multi-valued attribute)

To convert this table to 4NF, we need to remove the multi-valued attribute "Skills" and create a separate table called "EmployeeSkills" with the columns:
- EmployeeID (Foreign Key)
- Skill

6. Fifth Normal Form (5NF): Also known as Project-Join Normal Form (PJNF), this form deals with join dependencies and ensures that a database is free from redundancy caused by join operations.

Example:
Consider two tables called "Orders" and "Products" with the following columns:
- Orders: OrderID (Primary Key), ProductID (Primary Key), Quantity
- Products: ProductID (Primary Key), ProductName, SupplierID

To convert these tables to 5NF, we need to eliminate the join dependency between "Orders" and "Products". We can create a separate table called "OrderProducts" with the columns:
- OrderID (Foreign Key)
- ProductID (Foreign Key)
- Quantity

7. Domain-Key Normal Form (DK/NF): This form ensures that all constraints on a table are expressed as domain constraints and key constraints.

Example:
Consider a table called "Students" with the following columns:
- StudentID (Primary Key)
- Name
- Age

To ensure DK/NF, we need to express the constraint that "Age" should be a positive integer using domain constraints.

It is important to note that higher normal forms (e.g., 4NF, 5NF) are not always necessary or practical to achieve, and the appropriate level of normalization depends on the specific requirements and complexity of the database.