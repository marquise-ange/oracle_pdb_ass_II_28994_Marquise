Oracle PDB Assignment II
# Oracle PDB Assignment II

**Student Name:** Marquise Ange IREBE  
**Student ID:** 28994  
**Date:** 2026-02-17  

---

## Task 1: Create a New Pluggable Database

**Naming Convention Used:**

- **PDB Name:** ma_pdb_28994  
- **Username inside PDB:** marquise_plsqlauca_28994  

**Steps Performed:**

1. Connected to CDB as SYSDBA  
2. Created the PDB using appropriate SQL commands  
3. Opened the PDB in READ WRITE mode  
4. Created the user account with necessary privileges  
5. Verified successful creation and user login  

---

## Task 2: Create and Delete a Temporary PDB

**Naming Convention Used:**

- **Temporary PDB Name:** ma_to_delete_pdb_28994  

**Steps Performed:**

1. Created temporary PDB  
2. Verified PDB existence using `SHOW PDBS`  
3. Closed the PDB  
4. Dropped the PDB including datafiles  
5. Confirmed successful deletion  

---

## Task 3: Oracle Enterprise Manager (OEM)

**Steps Performed:**

1. Started OEM service  
2. Accessed OEM web interface  
3. Logged in with appropriate credentials  
4. Verified PDB status in dashboard  
5. Captured dashboard view showing completed tasks  

---

## Key SQL Commands Used

**PDB Creation**
```sql
-- Connect as SYSDBA
CREATE PLUGGABLE DATABASE ma_pdb_28994
  ADMIN USER pdb_admin IDENTIFIED BY 12345
  FILE_NAME_CONVERT = ('/pdbseed/', '/ma_pdb_28994/');

-- Open PDB
ALTER PLUGGABLE DATABASE ma_pdb_28994 OPEN;

-- Set PDB to auto-start
ALTER PLUGGABLE DATABASE ma_pdb_28994 SAVE STATE;


User Creation

-- Connect to PDB
ALTER SESSION SET CONTAINER = ma_pdb_28994;

-- Create user
CREATE USER marquise_plsqlauca_28994 IDENTIFIED BY 12345;
GRANT CONNECT, RESOURCE TO marquise_plsqlauca_28994;
GRANT UNLIMITED TABLESPACE TO marquise_plsqlauca_28994;


PDB Deletion

-- Close PDB
ALTER PLUGGABLE DATABASE ma_to_delete_pdb_28994 CLOSE IMMEDIATE;

-- Drop PDB
DROP PLUGGABLE DATABASE ma_to_delete_pdb_28994 INCLUDING DATAFILES;


Verification Commands

-- Check PDBs
SELECT pdb_name, status FROM dba_pdbs;

-- Check container name
SHOW CON_NAME;

-- Verify user creation
SELECT username FROM dba_users WHERE username = 'MARQUISE_PLSQLAUCA_28994';

Academic Integrity Statement

“All sources were properly cited. Implementations and analysis represent original work. No AI-generated content was copied without attribution or adaptation.”

Submission Information

GitHub Repository: https://github.com/yourusername/oracle_pdb_ass_II_28994_marquise/tree/main

Primary PDB Created: ma_pdb_28994

Temporary PDB Created & Deleted: ma_to_delete_pdb_28994

References

Oracle Database Documentation: Oracle Multitenant Architecture

Oracle Enterprise Manager Cloud Control Documentation

Course Materials: Database Development with PL/SQL (INSY 8311)
