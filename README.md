# Streamlining-Ticket-Assignment-For-Efficient-Support-Operations
🧾 Project Overview

This project implements an *automated ticket routing system* within *ServiceNow* for ABC Corporation. The goal is to improve operational efficiency by intelligently assigning support tickets to the appropriate support teams based on the issue type.

---

🎯 Objective

- Minimize delays in issue resolution.
- Improve customer satisfaction.
- Optimize resource utilization in the support department.
- Automate repetitive routing tasks using *ServiceNow Flows* and *Access Control Rules*.

---

## 🛠 Features

- 🔐 Create users, groups, and roles within ServiceNow.
- 📋 Custom table: Operations Related for tracking support issues.
- ✅ Role-based access control using ACLs.
- 🔄 Automated flow-based ticket assignment based on the issue type.
- 📱 Mobile module support.

---

## 🧩 Issue Types & Group Assignments

| Issue Type                        | Assigned Group   |
|----------------------------------|------------------|
| Regarding certificates           | Certificates     |
| Unable to login to platform      | Platform         |
| 404 error                        | Platform         |
| Regarding user expired           | Platform         |

---

## 🧪 Setup Instructions (ServiceNow)

### 👤 Create Users
1. Navigate to: All > Users (under System Security)
2. Click *New* and fill user details
3. Submit and repeat for additional users

### 👥 Create Groups
1. Go to: All > Groups
2. Add new groups such as Platform, Certificates

### 🔐 Create Roles
1. Navigate to: All > Roles
2. Add roles like Platform_role, Certificate_role

### 🗃 Create Table
- Label: Operations Related
- Enable: Create module and Create mobile module
- Add issue-related fields

### 🗂 Add Choice Values to Issues
Choices include:
- Unable to login to platform
- 404 error
- Regarding certificates
- Regarding user expired

---

## 👥 Assign Users & Roles to Groups

- Add users like Katherine Pierce to the Certificates group and assign Certificate_role.
- Add users like Manne Niranjan to the Platform group and assign Platform_role.

---

## 🔐 Configure Role Access to Table

- Use *Application Access* section of the Operations Related table.
- Require Platform_role and Certificate_role for read/write permissions.

---

## 🔒 Create ACL (Access Control)

1. Navigate to: All > Access Control (ACL)
2. Add 4 ACLs for table and fields
3. Require admin role

---

## 🔄 Create Flows (ServiceNow Flow Designer)

### Flow: Regarding Certificate
- Trigger: Record created/updated in Operations Related
- Condition: issue == Regarding certificates
- Action: Update assigned_to_group = Certificates

### Flow: Regarding Platform
- Trigger: Record created/updated in Operations Related
- Conditions:  
  issue == Unable to login to platform  
  issue == 404 error  
  issue == Regarding user expired
- Action: Update assigned_to_group = Platform

---

## ✅ Result

The system automatically assigns tickets based on issue type, enhancing service desk efficiency.

---

## 📌 Conclusion

This project successfully automates ticket routing in ServiceNow, improving resolution speed and team coordination. It provides a scalable solution that minimizes human error and manual interventions in support operations.

---

## 🛡 Technologies Used

- 💻 *ServiceNow Platform*
- ⚙ Flow Designer
- 🔐 ACL & Role-Based Access
- 🗃 Custom Tables and Forms

  ##  Demo video link:https://drive.google.com/file/d/1IbiH4ixk5-6tIUIo1_vnB50q1t4mt8I1/view?usp=drivesdk
