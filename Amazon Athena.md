# 🛡️ AWS Service: Amazon Athena

### 📖 What is it?
Amazon Athena is a **serverless** query engine that allows you to run SQL queries against large datasets stored in **Amazon S3**. You only pay for the amount of data scanned per query.

---

### 🚀 Various Use Cases
*   **Log Analysis:** Instantly query security logs like **AWS CloudTrail**, **VPC Flow Logs**, and **ELB Access Logs**.
*   **Security Auditing:** Run ad-hoc SQL queries to check for unauthorized API calls.
*   **Compliance Reporting:** Generate reports for PCI DSS or HIPAA by analyzing historical logs.

---

### ⚙️ How it is Configured (Security Focus)
*   **Workgroups:** Used to separate users and teams. You can enforce **encryption settings** at the workgroup level so users cannot override them.
*   **Query Result Encryption:** Athena stores results in S3. This directory **must be encrypted** using SSE-S3 or **SSE-KMS**.
*   **IAM Policies:** Controls who can run queries and which Glue Data Catalog tables they can see.

---

### 🎓 Exam-Related Notes (SCS-C03 Traps)
*   **Key Isolation:** Best practice is to use **different KMS keys** for the source data and the Athena query results.
*   **Data Masking:** **AWS Lake Formation** can be used with Athena to provide **row-level** or **column-level security**.
*   **Cost Optimization:** Partitioning data and using columnar formats like **Parquet** reduces data scanned and lowers your bill.

---

### 🔗 Integration with Other Services
*   **AWS Glue:** Athena uses the Glue Data Catalog to store table schemas.
*   **Amazon QuickSight:** Used to create security dashboards from Athena query results.
*   **Amazon Macie:** Macie discovery results can be queried via Athena to identify sensitive data.
