
# 🛡️ Enable Cross-Region Backup Replication for EC2 using AWS Backup

## 📌 Objective

This project demonstrates how to configure an **AWS Backup Plan** to automatically back up an EC2 instance in one region (e.g., `ap-south-1`) and **replicate the backups to another AWS region** (e.g., `ap-northeast-3`).  
This ensures **data durability**, **disaster recovery**, and **resilience** across geographically separated environments.

---

## 🧱 Project Tasks

### 1️⃣ EC2 Instance Setup
- Launched an EC2 instance in the primary region.
- Deployed a sample web application and uploaded test files.

### 2️⃣ AWS Backup Plan Creation
- Created a **Backup Vault** in the primary region.
- Built a **Backup Plan** named `EC2CrossRegionPlan` with:
  - A **daily backup rule**.
  - **Lifecycle rule** to transition backups to cold storage after 7 days.
  - **Resource assignment** linking the EC2 instance.

### 3️⃣ Cross-Region Backup Replication
- Enabled **Backup Copy** in the same plan.
- Set **destination region** to `ap-northeast-3`.
- Used **destination-vault** for replicated backups.
- Matched copy frequency and retention with source.

### 4️⃣ Validation
- Triggered an **on-demand backup**.
- Verified successful backup and copy jobs.
- Confirmed **Recovery Point** presence in destination region.

---

## 📸 Screenshots

- ✅ Primary and destination backup vaults  
- ✅ Backup plan & rule with cross-region copy settings  
- ✅ Completed backup and copy jobs  
- ✅ EC2 recovery point in destination region

---

## 📄 Summary Report (Highlights)

- **Why Cross-Region?**  
  Increases fault tolerance and supports compliance by keeping a replicated copy in a separate AWS region.

- **Benefits:**  
  - Business continuity  
  - Disaster recovery readiness  
  - Minimal manual effort (automation)

- **Challenges & Fixes:**  
  - IAM role not attached → Used `AWSBackupDefaultServiceRole`  
  - No EC2 showing in resource assign → Ensured region match between EC2 and Backup Plan

---

## 💼 Deliverables

- [x] `summary-report.txt`  
- [x] Screenshots folder  
- [x] Fully working Backup Plan in AWS  
- [x] `README.md` (this file)

---

## 👤 Author

**Prashant Gharate**  
GitHub: [prashantgharate](https://github.com/prashantgharate)
