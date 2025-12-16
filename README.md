# Coffee_Highland_Project

# Competitive Landscape Analysis & Brand Positioning
## Highlands Coffee – Data Modeling & Governance Project

---

## 📌 Project Overview
This project focuses on designing a clean, consistent, and business-driven data model
to support competitive landscape analysis and brand positioning for Highlands Coffee.

The solution integrates:
- Data cleaning and quality control
- Conceptual and logical data modeling (ER diagram design)
- Role-based data access control (RBAC)
- Business analytics and visualization

---

## 🎯 Business Objectives
- Eliminate data redundancy and inconsistent labels
- Design a centralized customer-centric data model (MPI-based)
- Support cross-functional analytics and decision-making
- Ensure data governance and access security

---

## 🧹 Data Cleaning & Quality Assurance

### 1. Redundancy Detection
- Removed duplicated demographic fields
- Centralized customer information into MPI entity

### 2. Label Consistency
- Standardized gender, segmentation, and time labels
- Unified naming conventions across tables

### 3. Constraint Validation
- Enforced valid value ranges (age, spending, frequency)
- Applied referential integrity rules

### 4. Missing Value Treatment
- Median/Mode imputation for demographics
- Category-based handling for behavioral attributes

### 5. Cross-table Consistency
- Validated segmentation alignment across brand and customer levels

---

## 🏗 Conceptual Data Model


### Core Design Principle
The **MPI (Customer)** entity acts as the central hub representing individual consumers.
All behavioral, perceptual, and segmentation entities relate to MPI via 1-to-many relationships.

### Key Entities
- Customer (MPI)
- Brand
- Brand_Health
- Brand_Image
- Segmentation
- Need_State
- Day_Part
- Day_Week
- Companion
- Competitor

---

### 🔗 Entity Relationships

| From Entity | To Entity | Cardinality | Business Logic |
|------------|----------|-------------|----------------|
| Customer | Brand_Health | 1 : N | Consumers evaluate multiple brands |
| Customer | Brand_Image | 1 : N | Brand perception varies by attribute |
| Customer | Segmentation | 1 : N | Multi-segment behavior |
| Customer | Day_Part | 1 : N | Time-based visits |
| Brand | Competitor | Market-level | Competitive benchmarking |

<img width="1149" height="551" alt="image" src="https://github.com/user-attachments/assets/f5f143b8-837b-4657-a7b4-55ea994c54d8" />
---

### 🧱 ER Diagram
```text
Customer (MPI)
 ├── Brand_Health
 ├── Brand_Image
 ├── Segmentation
 ├── Day_Part
 ├── Day_Week
 ├── Need_State
 └── Companion
```
<img width="1252" height="737" alt="image" src="https://github.com/user-attachments/assets/b947c095-8ef5-411a-ae4f-ee4b13e4537e" />


## 🔐 Role-Based Data Access Control (RBAC)
Defined Roles
```
- Board of Directors (BOD)
- HR / People Analytics
- Finance & Accounting
- Marketing
- CRM Lead
- Store Manager
- Regional Manager
- Sales Operations
```
<img width="1116" height="517" alt="image" src="https://github.com/user-attachments/assets/71cef139-1789-4dac-86bb-816311e6dde8" />


| Data Entity  | BOD | HR   | Finance | Marketing | CRM  | Store | Region | Sales Ops |
| ------------ | --- | ---- | ------- | --------- | ---- | ----- | ------ | --------- |
| Customer     | Agg | Reg  | None    | Full      | NPS  | Store | Region | Full      |
| Brand_Health | Agg | Reg  | KPI     | Full      | NPS  | Store | Region | Full      |
| Competitor   | Agg | None | Count   | Full      | None | None  | Region | Full      |


## 📊 Analytical Use Case
```
Customer churn pattern analysis

Brand perception impact on loyalty

Competitive positioning assessment

Segmentation-driven insights
```

# 🛠 Tools & Technologies
```
- SQL

- Data Modeling (ERD)

- Data Governance (RBAC)

- Business Analytics
```
