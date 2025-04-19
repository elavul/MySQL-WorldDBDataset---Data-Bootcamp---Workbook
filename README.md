# SQL-and-Databases---Data-Bootcamp---Workbook

**Focus:** Foundational SQL concepts, database theory, and practical SQL query execution using `world_db` dataset.  

---

## 🧠 **Weekly Breakdown**

---

#### ✅ **Day 1: Database Fundamentals**

**Task 1: Key Database Concepts**  
- **Primary Key:** Unique identifier in a table; no nulls or duplicates allowed.  
- **Secondary Key:** Non-unique, used for indexing and performance.  
- **Foreign Key:** Links child table to a parent table’s primary key.  
- **Examples of Relationships:**  
  - 1:1 → Person ↔ Passport  
  - 1:M → Department ↔ Employees  
  - M:M → Students ↔ Courses  

**Task 2: Relational vs Non-Relational Databases**  
- **Relational DB:** Structured schema (SQL); ideal for structured data.  
- **Non-Relational DB (NoSQL):** Schema-less; best for unstructured, dynamic, or large-scale data.  
- **Use Cases:**  
  - Relational → Employee records, Sales data  
  - Non-Relational → Social media posts, IoT sensor data  

---

#### ✅ **Day 3: SQL Join Types**

**Join Types Explained with Use Cases:**
- **SELF JOIN:** Hierarchical data (e.g., Employees and Managers in same table)  
- **RIGHT JOIN:** All Departments incl. those with no Employees  
- **FULL JOIN:** All Students and Courses (even unlinked ones)  
- **INNER JOIN:** Only matching records (e.g., Employees + Departments)  
- **CROSS JOIN:** Cartesian product (e.g., Color × Size)  
- **LEFT JOIN:** All Employees incl. unassigned ones  

---

#### ✅ **Day 4: SQL Practical**

**Dataset Used:** `world_db`  
**Key SQL Tasks & Business Scenarios:**

1. **Demographic Analysis:**  
 
   SELECT COUNT(city.Name) FROM city WHERE countrycode = 'USA';
  

2. **Health Data – Life Expectancy:**  
 
   SELECT Name, LifeExpectancy FROM country ORDER BY LifeExpectancy DESC;
  

3. **Marketing – Cities with "New":**  
   
   SELECT Name FROM city WHERE Name LIKE '%New%';
   

4. **Top 10 Populous Cities:**  
 
   SELECT Name, Population FROM city ORDER BY Population DESC LIMIT 10;
   

5. **Investment Research – Cities > 2M Population:**  

   SELECT Name FROM city WHERE Population > 2000000;
   

6. **Name Prefix Filtering (e.g., starts with 'Be'):**  
   
   SELECT Name FROM city WHERE Name LIKE 'Be%';
   
7. **Mid-Size City Analysis (500k–1M):**  
   
   SELECT Name FROM city WHERE Population BETWEEN 500000 AND 1000000;
   

8. **Alphabetical Sorting:**  
   
   SELECT Name FROM city ORDER BY Name ASC;
  

9. **Max Population City:**  
   
   SELECT Name FROM city ORDER BY Population DESC LIMIT 1;

10. **Name Frequency (Grouping):**  
    SELECT Name, COUNT(*) FROM city GROUP BY Name ORDER BY Name;
    

11. **Min Population City:**  
    SELECT Name FROM city ORDER BY Population ASC LIMIT 1;
    

12. **Country with Largest Population:**  
    SELECT Name FROM country ORDER BY Population DESC LIMIT 1;
    

13. **Capital of Spain:**  
    
    SELECT city.Name FROM country JOIN city ON country.Capital = city.ID WHERE country.Name = 'Spain';

14. **Cities in Europe:**  

    SELECT city.Name FROM city JOIN country ON city.CountryCode = country.Code WHERE country.Continent = 'Europe';
    

15. **Average Population by Country:**  
    SELECT country.Name, AVG(city.Population) FROM country JOIN city ON country.Code = city.CountryCode GROUP BY country.Name;
    

16. **Capital Cities by Region:**  
    SELECT Region, city.Name, city.Population FROM country JOIN city ON country.Capital = city.ID;
    

17. **Low Population Density Countries:**  
    SELECT Name, Population, (Population / SurfaceArea) AS Density FROM country ORDER BY Density ASC;
    

18. **Cities with High GDP per Capita (Estimated):**  
    SELECT Name, (Population / NULLIF(SurfaceArea, 0)) AS GDP FROM country ORDER BY GDP DESC;

19. **Pagination – Rows 31–40 by Population:**  
    SELECT Name FROM city ORDER BY Population DESC LIMIT 10 OFFSET 30;

---

#### ✅ **Day 4: Optional Essay Task**
**Topic:** Designing a database system for a retail business (e.g., groceries & household items)  
**Expected Sections:**  
- Business needs  
- Table relationships (e.g., `Sales`, `Customers`, `Inventory`)  
- Schema design  
- SQL `CREATE`, `INSERT`, `JOIN` examples  
- Maintenance, backup, and data integrity strategy  

---

### 🧰 **Tools Used**  
- SQL (MySQL or similar)  
- `world_db` dataset  

---

### 📂 **Folder Structure Recommendation for GitHub**

```bash
📁 data-technician-week3-sql/
├── 📄 README.md
├── 📄 Data_Technician_Workbook_Week_3_Summary.sql
├── 📁 screenshots/
│   └── *.png (if applicable)
├── 📁 datasets/
│   └── world_db/
```
