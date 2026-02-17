# oracle_pdb_ass_II_28994_Marquise
# Task 1: Create a New Pluggable Database (PDB)

## Student Information
- Student Name: Marquise
- Student ID: 28994

---

## Objective
Create a permanent Pluggable Database (PDB) and configure a user account that will be used for all future class work.

---


## User Details Inside the PDB
- Username: marquise_plsqlauca_28994
- Password: 12345
- Privileges Granted: CONNECT, RESOURCE

---

## Commands Executed

### 1. Connect as SYSDBA
```sql
CONNECT / AS SYSDBA;
. Open the PDB
ALTER PLUGGABLE DATABASE JO_PDB_29181 OPEN;

3. Verify PDB Status
SHOW PDBS;

4. Switch to the PDB
ALTER SESSION SET CONTAINER = JO_PDB_29181;

5. Create User
CREATE USER marquise_plsqlauca_28994 IDENTIFIED BY 12345;

6. Grant Privileges
GRANT CONNECT, RESOURCE TO marquise_plsqlauca_28994;

7. Verify User Creation
SELECT username FROM dba_users 
WHERE username = 'MARQUISE_PLSQLAUCA_28994';

Evidence

Screenshots provided showing:

PDB opened in READ WRITE mode

User creation

Privileges granted

Username visible in DBA_USERS




