@snap[text-center]
# Database Normalization
#### Crash Course 
@snapend

Note:
- https://gitpitch.com/kk-sw/database-normalization/master?grs=github&t=moon#/
- https://support.microsoft.com/hu-hu/help/283878/description-of-the-database-normalization-basics
- https://en.wikipedia.org/wiki/Database_normalization

---
  
### Database Normalization

- By Codd (again)
- Reduce data redundancy 
- Improve data integrity
- Based on formal rules
- ~10 Normal Forms (NF)
    - Real life ~3NF
    - Based on experience
@ul
- Denormalization (performance)
@ulend

---

## Original Data

PupilId|Mentor|MentorOffice|1. less|2. less|3. less
------|------|-----------|-------|-------|-----------
1022  |John  |412        |101-07 |143-01 |159-02
4123   |Basil |216        |201-01 |211-02 |214-01

*Primary Key (PK)* is an **unique** identifier for an entity.

---

## 1NF - No Repeating Groups/Attrib. 

PupilId|Mentor|MentorOffice|Less.Id
-------|------|-----------|-------
1022   |   John    |412    |101-07
1022   |   John    |412    |143-01
1022   |   John    |412    |159-02
4123   |   Basil   |216    |201-01
4123   |   Basil   |216    |211-02
4123   |   Basil   |216    |214-01

Note:
- Lesson from Col->Row
- Primary Key

---

## 2NF - No Redundancy

PupilId |Mentor |MentorOffice
--------|-------|------------
1022    |John   |412
4123    |Basil  |216


PupilId |Less.Id
--------|------
1022    |101-07
1022    |143-01
4123    |201-01
... | ...

Note:
- Remove Duplicates (same data in rows at col pos.)
- PupilId as key
- Remaining into new table 
- Not all data shown

---

## 3NF - No Key Dep. (Func. Correctness) 

PupilId |Mentor
--------|------
1022    |John
4123    |Basil


Mentor  |MentorOffice
--------|------
John    |412
Basil   |216


Note:
- `Mentor` table 

---

## 4NF And Beyond

@ul
- Complex to design with not much gain
- Not common in real life
    - Used in special domains
@ulend

---

@snap[text-center]
# Thank You
#### Questions? 
@snapend
