
# [Guided Journeys] – Technical Documentation

> **How to use this template:** Replace every section in square brackets `[ ]` with content specific to your project. Remove any sections that are not applicable, and add additional sections as needed.

---

## Table of Contents

1. [Project Overview](#1-project-overview)
2. [Stakeholders](#2-stakeholders)
3. [Benefits of the Project](#3-benefits-of-the-project)
4. [Architecture & Technical Design](#4-architecture--technical-design)
5. [Data Sources & Tables](#5-data-sources--tables)
6. [Data Quality Issues & Known Limitations](#6-data-quality-issues--known-limitations)
7. [Usage Guide](#7-usage-guide)
8. [Security & Access Control](#8-security--access-control)
9. [Testing & Validation](#9-testing--validation)
10. [Deployment & Maintenance](#10-deployment--maintenance)
11. [Change Log / Version History](#11-change-log--version-history)
12. [Glossary](#12-glossary)
13. [References & Related Documents](#13-references--related-documents)

---

## 1. Project Overview

| Field              | Details                                      |
|--------------------|----------------------------------------------|
| **Project Name**   | [Guided journey]                          |
| **Version**        | [v1]                               |
| **Status**         | [In development]    |
| **Owner**          | [Owen's data science team]             |
| **Last Updated**   | [2026-05-18]                                 |
| **Repository**     | [Link to source control repository]          |
| **Related Tickets**| [https://dev.azure.com/CentricaEngineeringServices/Chief_Data_Analytics_Office_Workstack/_boards/board/t/Chief_Data_Analytics_Office_Workstack%20Team/Stories?System.AssignedTo=%40me&workitem=263731]  |

### 1.1 Purpose

The purpose of this project is to get some insight into the guided journeys currently in place - e.g how many people are using each journey, 
numbers of drop out at each stage in the journey, an understanding of the different journeys and what they look like. 
Overall, there are two purposes: 
- Understand how the current guided journeys are being tracked, and work. Provide in depth analysis.
- Feedback data quality problems / logistical issues in how the journeys are tracked to influence how new guided journeys will be tracked. 

### 1.2 Background / Problem Statement

The problem that prompted this project is that guided journeys have been implemented and are being used and data tracked, but this data is not being used 
to inform anything. This means we have no real way of knowing how effective the guided journeys are and how they should be altered. 

### 1.3 Scope

**In Scope:**
- Creating an analytics framework to understand the implemented guided journeys  
- Improve future implementations 

**Out of Scope:**
- Change of data tracking for previous guided journeys (retroactive) 

---

## 2. Stakeholders

### 2.1 Stakeholder Matrix

| Role                  | Name / Team              | Responsibility                                          | Contact                    |
|-----------------------|--------------------------|---------------------------------------------------------|----------------------------|
| **Stakeholder**     | [Dave Woodhouse]            | Final decision-making authority                       | [email or channel]       |
| **Data Analyst/ Scientist**      | [Stefanie Pieterse / Owen Allenden's team]            | Consumes and interprets data / builds reports           | [email or channel]         |
| **End Users**         | [Internal use / agent use]     | Day-to-day users of the output                          | [email or channel]         |

## 3. Benefits of the Project

### 3.1 Business Benefits

| Benefit                        | Description                                                              | Measurement / KPI                   |
|--------------------------------|--------------------------------------------------------------------------|--------------------------------------|
| [Benefit 1]                    | [e.g., Reduces manual reporting effort]                                  | [e.g., Hours saved per month]        |
| [Benefit 2]                    | [e.g., Provides single source of truth for sales data]                   | [e.g., Reduction in data discrepancies] |
| [Benefit 3]                    | [e.g., Enables faster decision-making]                                   | [e.g., Report refresh time < 30 min] |

### 3.2 Technical Benefits

- [e.g., Consolidates data from multiple disparate sources into one platform]
- [e.g., Automates a previously manual ETL process, reducing error risk]
- [e.g., Improves data pipeline reliability with automated testing and monitoring]

### 3.3 Strategic Alignment

Will allow for reduction in repeat contacts, inefficiencies in calls, AHT etc ->  aligns with CST (customer service transformation) to reduce contacts

---

## 4. Architecture & Technical Design

### 4.1 High-Level Architecture

[Insert or link to an architecture diagram (e.g., draw.io, Lucidchart, Miro).  
Describe the main components and how they interact.]

### 4.3 Data Flow

[Describe, step by step, how data moves from source to destination.  
Include frequency, method of transfer, and any transformations applied at each stage.]

1. **Extraction:** [Data is extracted from [source] using [method] on [schedule].]
2. **Loading:** [Raw data is loaded into [staging area / raw zone].]
3. **Transformation:** [Data is cleaned, enriched, and modelled using [tool/logic].]
4. **Publishing:** [Curated data is published to [destination] for consumption.]


## 5. Data Sources & Tables

### 5.2 Data Tables / Objects

For each table, document the following:

---

#### Table: `[ods_p_salesforce_energy.sf_DiagnosticReporting__]`

| Property           | Details                                              |
|--------------------|------------------------------------------------------|
| **Description**    | [Guided journey information]                           |
| **Source**         | [salesforce calls]                          |
| **Row Grain**      | [a page visited / triggered in the journey ] |

**Column Definitions:**

<img width="827" height="558" alt="Screenshot 2026-05-18 at 14 32 14" src="https://github.com/user-attachments/assets/98d9c03d-8fb8-405f-8e2a-2edf107b7352" />


**Business Rules & Transformations applied to this table:**
- [e.g., `amount` is converted from USD to ZAR using the exchange rate on `exchange_rate_table`.]
- [e.g., Records with `status = 'Deleted'` are excluded from the curated layer.]

---

*[Repeat the above table block for each additional table/object.]*

### 5.3 Entity Relationship Diagram (ERD)

<img width="453" height="608" alt="Screenshot 2026-05-18 at 15 44 30" src="https://github.com/user-attachments/assets/bbd77c90-06df-496a-b6d2-d6837e28d4af" />

---

## 6. Data Quality Issues & Known Limitations

### 6.1 Data Quality Rules

| Rule ID | Table / Column           | Rule Description                                             | Severity        | Action on Failure               |
|---------|--------------------------|--------------------------------------------------------------|-----------------|---------------------------------|
| DQ-001  | `[table].[column]`       | [e.g., `customer_id` must not be NULL]                       | Critical        | [e.g., Reject row / Alert team] |
| DQ-002  | `[table].[column]`       | [e.g., `amount` must be greater than 0]                      | Warning         | [e.g., Flag for review]         |
| DQ-003  | `[table].[column]`       | [e.g., `status` must be one of: Active, Inactive, Pending]   | Warning         | [e.g., Default to 'Unknown']    |

### 6.2 Known Data Quality Issues

| Issue ID | Description                                                                          | Affected Table(s) / Column(s) | Impact                                    | Workaround / Resolution                      | Status        | Owner         |
|----------|--------------------------------------------------------------------------------------|-------------------------------|-------------------------------------------|----------------------------------------------|---------------|---------------|
| KDQ-001  | [e.g., ~2% of records have a NULL `region_code` due to a gap in the source system]   | `[table].[region_code]`       | [e.g., Region-level reports are incomplete] | [e.g., Default to 'UNKNOWN'; fix raised with source team] | Open  | [Team]        |
| KDQ-002  | [e.g., Historical data prior to 2020-01-01 has inconsistent date formats]            | `[table].[transaction_date]`  | [e.g., Date filters may exclude old data] | [e.g., Apply parsing logic in staging]       | Resolved      | [Team]        |

### 6.3 Known Limitations

- [e.g., Data is refreshed once daily; near-real-time reporting is not supported.]
- [e.g., Source system does not provide deletes; deleted records remain in the dataset until a full reload is run.]
- [e.g., Currency conversion uses end-of-day rates; intraday fluctuations are not captured.]

---

## 7. Usage Guide

### 7.1 How to Access

[Describe how different user groups gain access to the data or report, including any approval processes.]

| Access Method          | URL / Path / Tool                        | Who                              |
|------------------------|------------------------------------------|----------------------------------|
| Power BI Report        | [Link to report]                         | [Business users via AD group X]  |
| Snowflake / SQL        | `[database].[schema].[table_name]`       | [Analysts via role Y]            |
| API Endpoint           | `https://[base-url]/api/[endpoint]`      | [Developers via API key]         |
| File Export            | `[SharePoint / S3 path]`                 | [Finance team]                   |

### 7.2 Common Use Cases & Queries

#### Use Case 1: [Description, e.g., Monthly Sales Summary]

```sql
-- [Brief description of what this query does]
SELECT
    DATE_TRUNC('month', order_date) AS month,
    region,
    SUM(amount)                     AS total_sales
FROM [schema].[fact_orders]
WHERE status = 'Completed'
GROUP BY 1, 2
ORDER BY 1, 2;
```

#### Use Case 2: [Description]

```sql
-- [Add additional example queries as needed]
```

### 7.3 Filters & Parameters

| Parameter / Filter     | Description                                                     | Default Value     | Valid Values / Format            |
|------------------------|-----------------------------------------------------------------|-------------------|----------------------------------|
| `start_date`           | Start of the reporting period                                   | First day of month| `YYYY-MM-DD`                     |
| `end_date`             | End of the reporting period                                     | Today             | `YYYY-MM-DD`                     |
| `region`               | Filter by geographic region                                     | All regions       | See `dim_region` for valid values|

### 7.4 Interpreting the Output

[Explain how to read and interpret the data or report. Call out any metrics, calculations, or columns that require special explanation.]

| Metric / Column        | Definition                                                      | Notes / Caveats                              |
|------------------------|-----------------------------------------------------------------|----------------------------------------------|
| `total_sales`          | Sum of completed order amounts in local currency                | Excludes cancelled and refunded orders        |
| `conversion_rate`      | Percentage of leads that converted to a sale                    | Based on first-touch attribution              |

---

## 8. Security & Access Control

### 8.2 Access Control

| Role / AD Group        | Access Level                | Justification                                 |
|------------------------|-----------------------------|-----------------------------------------------|
| `[AD Group / Role 1]`  | Read (curated layer)        | Business users consuming reports              |
| `[AD Group / Role 2]`  | Read/Write (staging layer)  | Data engineers managing pipelines             |
| `[AD Group / Role 3]`  | Admin                       | Data platform administrators                  |

---
## 11. Change Log / Version History

| Version | Date       | Author         | Description of Change                                              |
|---------|------------|----------------|---------------------------------------------------------------------|
| 1.0.0   | [YYYY-MM-DD] | [Name]       | Initial release                                                    |
| 1.1.0   | [YYYY-MM-DD] | [Name]       | [e.g., Added new `region` dimension table]                         |
| 1.2.0   | [YYYY-MM-DD] | [Name]       | [e.g., Fixed DQ-001 – NULL region_code issue resolved at source]   |

---

## 12. Glossary

| Term / Acronym         | Definition                                                                  |
|------------------------|-----------------------------------------------------------------------------|
| ETL                    | Extract, Transform, Load – the process of moving and shaping data           |
| ELT                    | Extract, Load, Transform – data is loaded raw before transformation         |
| PII                    | Personally Identifiable Information                                         |
| SLA                    | Service Level Agreement – agreed performance targets                        |
| UAT                    | User Acceptance Testing                                                     |
| RACI                   | Responsible, Accountable, Consulted, Informed – a responsibility matrix     |
| KPI                    | Key Performance Indicator                                                   |
| DQ                     | Data Quality                                                                |
| [Add project-specific terms below]                                                              |
| [Term]                 | [Definition]                                                                |

---

## 13. References & Related Documents

| Document / Resource          | Description                                       | Link / Location                    |
|------------------------------|---------------------------------------------------|------------------------------------|
| [Source System Documentation]| Technical documentation for the source system    | [Link]                             |
| [Data Dictionary]            | Full data dictionary for the data platform       | [Link]                             |
| [Architecture Decision Record]| Key design decisions for this project           | [Link]                             |
| [Project Charter / Brief]    | Original project scope and approval document     | [Link]                             |
| [Related Report / Dashboard] | Downstream report that consumes this data        | [Link]                             |

---

*Document Owner: [Name / Team] | Last Reviewed: [YYYY-MM-DD] | Next Review Due: [YYYY-MM-DD]*

---

