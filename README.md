# 💊 Disease2Dose: A Comprehensive Medicine Information and Recommendation System

A full-stack database management system that offers centralized, accessible, and reliable information about medicines, pharmaceutical companies, and doctors. Developed as a group project for the Database Management Systems course (UCS310).

---

## 📌 Problem Statement

Patients, pharmacists, and doctors often face issues like:

- Difficulty finding reliable medicine details and alternatives
- Uncertainty about availability of medicines in nearby pharmacies
- Lack of a ranking system for pharmaceutical companies
- Challenges in identifying specialist doctors for specific diseases

---

## 💡 Solution Overview

**Disease2Dose** is designed to solve these problems by creating a centralized database system with:

- 🔍 Medicine search by disease, brand, composition, and ranking  
- 💊 Alternative medicine suggestions based on composition and price  
- 🏥 Real-time stock checking in pharmacies  
- ⭐ Pharmaceutical company ranking based on trust, quality, and reviews  
- 🧑‍⚕️ Doctor recommendations based on specialization and experience  

---

## 🧩 Database Design

### 🧠 ER Diagram  
Includes entities: Medicines, Diseases, Pharmacies, Companies, Doctors, Compositions, Stock.

### 🔄 Relationships
- One-to-many between Company → Medicines  
- Many-to-many between Doctors ↔ Diseases, Medicines ↔ Compositions  
- Stock linking Medicines ↔ Pharmacies  

### 🔎 Normalization
- All tables normalized to **3NF**
- Functional dependencies are properly addressed using primary and foreign keys

---

## 💾 SQL Schema Highlights

```sql
CREATE TABLE Medicines (
  Medicine_ID INTEGER PRIMARY KEY,
  Name VARCHAR(100),
  Type VARCHAR(50),
  Price NUMERIC(10,2),
  Rank INTEGER,
  Disease_ID VARCHAR(10),
  Company_ID INTEGER,
  FOREIGN KEY (Disease_ID) REFERENCES Disease(Disease_ID),
  FOREIGN KEY (Company_ID) REFERENCES Companies(Company_ID)
);

