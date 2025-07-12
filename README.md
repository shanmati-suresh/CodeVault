# 📘 CodeVault - DBMS Mini Project

A Database Management System (DBMS) mini project simulating a lightweight version control platform similar to GitHub. CodeVault allows users to manage repositories, track commits, handle merge requests, and perform code reviews using a relational database model.


## 📂 Project Structure

- **ER Diagram**: Models the relationships between entities like Users, Commits, Repositories, Reviews, and Merge Requests.
- **Relational Schema**: Defines the schema for all tables with keys and data types.
- **Normalization**: Achieved up to **3rd Normal Form (3NF)** to ensure data integrity and minimize redundancy.

---

## 📊 Database Tables

### 1. `Users`
Stores user details.
- `user_id` (PK)
- `username`
- `role` (developer/reviewer/etc.)

### 2. `Repositories`
Stores information about user-created repositories.
- `repo_id` (PK)
- `repo_name`
- `url`
- `user_id` (FK → Users)

### 3. `Commits`
Tracks code changes submitted by users.
- `commit_id` (PK)
- `repo_id` (FK → Repositories)
- `user_id` (FK → Users)
- `branch_name`
- `timestamp`

### 4. `Reviews`
Handles peer review of commits.
- `review_id` (PK)
- `commit_id` (FK → Commits)
- `reviewer_id` (FK → Users)
- `status` (Approved/Rejected)
- `comments`

### 5. `Merge_Requests`
Tracks the status of code merges.
- `merge_request_id` (PK)
- `commit_id` (FK → Commits)
- `status` (Pending/Merged/Rejected)
- `timestamp`

---

## ✅ Normalization Summary

The database is normalized up to **Third Normal Form (3NF)**:
- **1NF**: Atomic values, unique rows.
- **2NF**: Full functional dependency on primary keys.
- **3NF**: No transitive dependencies.

---

## 🛠️ Future Enhancements

- Implement issue tracking
- Add access control via permission table
- Add pull request discussions and code diffs
- Integrate web frontend for user interaction

---

## 📁 Tools Used

- **Database**: MySQL 
- **Design**: ERDPlus / dbdiagram.io for ER diagrams
- **Environment**: SQL IDE (e.g., MySQL Workbench)

---



