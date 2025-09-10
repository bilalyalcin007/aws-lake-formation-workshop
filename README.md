# 🚀 AWS Lake Formation Workshop

This repository documents my hands-on build of a **secure data lake** using AWS Lake Formation, Glue, Athena, and EMR.  
It includes setup, fine-grained access control, ETL jobs, and queries run via Athena.

![Title](screenshots/Title.png)

---

## 📂 Repo Structure
```
├── architecture/        # Diagrams (if any)
├── screenshots/         # AWS Console screenshots
├── LICENSE
└── README.md
```

---

## 📝 What I did (step-by-step)

### 1) CloudFormation Setup
- Launched 2 stacks (`Lake-Formation-Workshop`, `Lake-Formation-With-EMR-RuntimeRole-Workshop`).
- Automatically created IAM users, roles, and S3 buckets.  

📸 Screens:  
![CloudFormation Resources](screenshots/CloudFormation_Resources.png)  
![CloudFormation Outputs](screenshots/Cloudformation_Outputs.png)  
![CloudFormation Stack 2 Resources](screenshots/CloudFormation_Stack_2_Resources.png)  
![CloudFormation Stack 2 Outputs](screenshots/Cloudformation_stack_2_Outputs.png)  

---

### 2) Lake Formation Setup
- Created `tpc` database.  
- Registered tables from Glue Data Catalog.  
- Defined LF-Tags and applied to sensitive columns.  

📸 Screens:  
![Database Creation](screenshots/Database_TCP_Creation.png)  
![Database Tables](screenshots/Database_Tables.png)  
![Customer Table LF-Tags](screenshots/customer_table_lf_tags.png)  
![LF-Tag Success](screenshots/Database_Tables.png)  

---

### 3) Fine-Grained Access
- Created data filters (row-level, column-level).  

📸 Screens:  
![Column-level Access](screenshots/column_level_access.png)  
![Fine-Grained Access Granted](screenshots/Fine_Granted_Access.png)  

---

### 4) EMR & Runtime Roles
- Launched EMR cluster with runtime roles.  
- Submitted steps to test permissions (read/write/select).  

📸 Screens:  
![EMR Steps](screenshots/EMR_Steps.png)  

---

### 5) Glue ETL Job
- Built Glue Studio ETL pipeline (S3 → SQL Transform → S3).  

📸 Screens:  
![Glue ETL Job](screenshots/ETL.png)  

---

### 6) Athena Queries
- Queried `dl_tpc_item` and `dl_tpc_web_page` tables.  

📸 Screens:  
![Athena Query 1](screenshots/Athena_Query_1.png)  
![Athena Query 1 Result](screenshots/Athena_Query_1_REsult.png)  
![Athena Query 2](screenshots/Athena_Query_2.png)  
![Athena Query 2 Result](screenshots/Athena_Query_2_Result.png)  
