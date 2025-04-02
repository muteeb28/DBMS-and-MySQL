### **MySQL Basics: Q&A-Style Notes**  

---

#### **Q: How do I access the MySQL console?**  
**Steps**:  
1. **Check MySQL version** (optional):  
   ```bash  
   mysql --version  
   ```  
2. **Log in**:  
   ```bash  
   mysql -u root -p  
   ```  
   → Enter your password when prompted.  
3. **You’re in!** The MySQL console is ready for commands.  

---

#### **Q: How to list/show databases?**  
```sql  
SHOW DATABASES;  
```  
→ Displays all databases on the server.  

---

#### **Q: How to clear the console or list files?**  
- **Clear screen**:  
  ```sql  
  \! clear  # Clears the MySQL console  
  ```  
- **List directory files**:  
  ```sql  
  \! ls     # Shows files in the current directory  
  ```  

---

#### **Q: How to create or delete a database?**  
- **Create**:  
  ```sql  
  CREATE DATABASE filmsdatabase;  
  ```  
- **Delete**:  
  ```sql  
  DROP DATABASE filmsdatabase;  
  ```  

---

#### **Q: How to create a table?**  
1. **Select the database first**:  
   ```sql  
   USE filmsdatabase;  
   ```  
2. **Define the table**:  
   ```sql  
   CREATE TABLE movies (  
       Name VARCHAR(50),  
       Rating INT  
   );  
   ```  

---

#### **Q: How to view a table’s structure?**  
```sql  
DESC movies;  
```  
→ Shows columns, data types, and constraints.  

---

#### **Q: How to insert data into a table?**  
**Wrong Approach**: Skipping column names → Risk of mismatched data!  
```sql  
INSERT INTO movies VALUES (4, "Avengers");  # Error-prone!  
```  

**Best Practice**: **Specify columns** to ensure correct mapping.  
```sql  
-- Column order defines value assignment  
INSERT INTO movies (Name, Rating) VALUES ("Avengers", 4);  
-- Swapped columns? Adjust values accordingly:  
INSERT INTO movies (Rating, Name) VALUES (4, "Avengers");  
```  

**Insert multiple rows**:  
```sql  
INSERT INTO movies (Rating, Name) VALUES  
  (3, "Thor Love and Thunder"),  
  (5, "Iron Man"),  
  (5, "Avengers Endgame");  
```  

---

#### **Q: How to view data from a table?**  
- **All columns**:  
  ```sql  
  SELECT * FROM movies;  
  ```  
- **Specific columns**:  
  ```sql  
  SELECT Name FROM movies;          -- Only names  
  SELECT Rating, Name FROM movies;  -- Both columns  
  ```  

---

### **Practical Example: University Database**  
1. **Create database**:  
   ```sql  
   CREATE DATABASE universitydb;  
   USE universitydb;  
   ```  
2. **Create tables**:  
   ```sql  
   CREATE TABLE students (  
       StudentID INT PRIMARY KEY,  
       Name VARCHAR(100),  
       Age INT,  
       Major VARCHAR(50)  
   );  
   ```  
   ```sql  
   CREATE TABLE enrollments (  
       EnrollmentID INT PRIMARY KEY,  
       StudentID INT,  
       CourseID INT,  
       FOREIGN KEY (StudentID) REFERENCES students(StudentID)  
   );  
   ```  

---

### **Common Pitfalls & Fixes**  
| **Mistake**                     | **Fix**                              |  
|----------------------------------|--------------------------------------|  
| Forgetting `USE database;`       | Always select the database first.    |  
| Skipping column names in `INSERT`| **Always specify columns** for safety.|  
| Typos in commands                | Use `DESC table;` to verify structure.|  

---

### **Quick Reference Table**  
| **Action**               | **Command**                                 |  
|--------------------------|---------------------------------------------|  
| List databases           | `SHOW DATABASES;`                           |  
| Create database          | `CREATE DATABASE name;`                     |  
| Delete database          | `DROP DATABASE name;`                       |  
| Create table             | `CREATE TABLE name (col1 type, col2 type);` |  
| Insert data              | `INSERT INTO table (cols) VALUES (vals);`   |  
| View data                | `SELECT * FROM table;`                      |  

---

### **Mnemonics**  
- **“CREATE first, USE always”**: Create a database before using it.  
- **“SELECT * = See All Stars”**: `*` fetches all columns.  
- **“INSERT Columns First”**: Avoid data mismatches.  

---

### **Why This Works**  
- **Self-explanatory**: Commands are paired with context (e.g., `USE` before creating tables).  
- **Future-proof**: Explicit column names protect against schema changes.  

