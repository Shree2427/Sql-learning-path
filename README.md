# Sql-learning-path
<span style="font-size:18px; font-weight:bold;">A database</span> is an organized collection of data that allows you to store, manage, and retrieve information efficiently.

### Real-life Examples of Databases:
- **School Management System:** Stores student information, courses, grades, etc.  
- **E-commerce Website:** Maintains customer details, product catalogs, and order history.  
- **Banking System:** Tracks accounts, transactions, and customer information.

<h3>Why Do We Use Databases?</h3>
<ul>
  <li><b>Data Organization:</b> Keeps related data grouped and structured.</li>
  <li><b>Quick Access:</b> Allows fast retrieval and manipulation of data.</li>
  <li><b>Security:</b> Controls access to sensitive information.</li>
  <li><b>Scalability:</b> Can grow with your data needs.</li>
  <li><b>Data Integrity:</b> Ensures the accuracy and consistency of data.</li>
</ul>

<h3>Types of Databases</h3>
<ul>
  <li><b>Relational Database (RDBMS):</b> Data is stored in tables with rows and columns (e.g., MySQL, PostgreSQL).</li>
  <li><b>NoSQL Database:</b> Used for unstructured or semi-structured data (e.g., MongoDB, Cassandra).</li>
</ul>

<h3>Common Database Terms</h3>
<ul>
  <li><b>Table:</b> A collection of related data in rows and columns.</li>
  <li><b>Record (Row):</b> A single entry in a table.</li>
  <li><b>Field (Column):</b> A specific piece of information in a record.</li>
  <li><b>Primary Key:</b> A unique identifier for a record.</li>
  <li><b>Foreign Key:</b> A reference to a primary key in another table.</li>
</ul>
<h3>Difference between DBMS and RDBMS</h3>
<table>
  <tr>
    <th>Feature</th>
    <th>DBMS (Database Management System)</th>
    <th>RDBMS (Relational Database Management System)</th>
  </tr>
  <tr>
    <td>Data Structure</td>
    <td>Data is stored as files.</td>
    <td>Data is stored in tables (rows and columns).</td>
  </tr>
  <tr>
    <td>Relationships</td>
    <td>No relationships between data.</td>
    <td>Supports relationships between tables (foreign keys).</td>
  </tr>
  <tr>
    <td>Data Integrity</td>
    <td>Low data integrity.</td>
    <td>High data integrity (follows normalization rules).</td>
  </tr>
  <tr>
    <td>Query Language</td>
    <td>No standard query language (some support SQL).</td>
    <td>Uses SQL as a standard query language.</td>
  </tr>
  <tr>
    <td>Transactions</td>
    <td>May not support ACID properties.</td>
    <td>Fully supports ACID properties for transaction management.</td>
  </tr>
  <tr>
    <td>Examples</td>
    <td>XML Database, Hierarchical Database</td>
    <td>MySQL, PostgreSQL, Oracle, SQL Server</td>
  </tr>
</table>

<h3>ACID Properties (Key for Transaction Management in RDBMS)</h3>
<ul>
  <li><b>Atomicity:</b> All or nothing: A transaction is either fully completed or not executed at all.<br>
  <b>Example:</b> In a banking system, transferring money from Account A to Account B involves two steps—debit from A and credit to B. If one fails, the entire transaction is rolled back.</li>
  
  <li><b>Consistency:</b> Ensures the database remains in a valid state before and after the transaction.<br>
  <b>Example:</b> If a transaction updates a student's grade, it must comply with grading rules (e.g., grades between A and F).</li>
  
  <li><b>Isolation:</b> Transactions are executed independently to prevent interference.<br>
  <b>Example:</b> Two users trying to update the same product price won’t affect each other. Each transaction is isolated.</li>
  
  <li><b>Durability:</b> Once a transaction is committed, it remains permanent, even in case of power failures or crashes.<br>
  <b>Example:</b> After updating a customer order, the change persists even if the system crashes right after.</li>
</ul>
<h2>SQL Queries for Student Management</h2>

  <h3>1. Find students born after January 1, 2000</h3>
  <pre>
SELECT * FROM students WHERE dob > '2000-01-01';
  </pre>

  <h3>2. Update the email of a student with <code>usn = 'S003'</code></h3>
  <pre>
UPDATE students 
SET email = 'newalice@example.com' 
WHERE usn = 'S003';
  </pre>

  <h3>3. Delete the student with <code>usn = 'S005'</code></h3>
  <pre>
DELETE FROM students 
WHERE usn = 'S005';
  </pre>

  <h3>📚 Aggregate Functions & Grouping</h3>

  <h4>4. Count the total number of students</h4>
  <pre>
SELECT COUNT(*) AS total_students FROM students;
  </pre>

  <h4>5. Find the earliest date of birth</h4>
  <pre>
SELECT MIN(dob) AS earliest_dob FROM students;
  </pre>

  <h4>6. Group students by year of birth and count how many students were born each year</h4>
  <pre>
SELECT YEAR(dob) AS birth_year, COUNT(*) AS total_students
FROM students
GROUP BY YEAR(dob);
  </pre>

