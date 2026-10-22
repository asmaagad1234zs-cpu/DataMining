# DataMining
Building a modern data warehouse with SQL Server
# Cybersecurity Risk & Behavior Lakehouse

**An integrated data warehouse for cybersecurity analytics, user behavior analysis, and risk assessment.**

## 📌 Project Overview

The Cybersecurity Risk & Behavior Lakehouse is a data mining project designed to integrate multiple cybersecurity data sources into a unified analytical platform.

Cybersecurity teams often analyze user access permissions, web browsing activity, insider-threat indicators, and endpoint vulnerabilities separately. This separation makes it difficult to identify security risks that emerge from the combination of several factors.

This project proposes a **Medallion Architecture (Bronze, Silver, and Gold)** to consolidate these data sources, prepare them for analysis, and support data-driven cybersecurity risk assessment.

The ultimate goal is to identify suspicious user behavior and calculate meaningful risk scores based on user privileges, browsing behavior, and known software vulnerabilities.

## 🎯 Project Objectives

- Integrate heterogeneous cybersecurity datasets into a unified data warehouse.
- Clean, standardize, and transform raw data using SQL.
- Connect related records across datasets using appropriate identifiers and timestamps.
- Design dimensional models using a Star Schema.
- Detect anomalous browsing patterns and potentially suspicious user behavior.
- Assess cybersecurity risk using user permissions, website risk indicators, and endpoint vulnerabilities.
- Prepare analytical tables for dashboards, reporting, and future security monitoring applications.

## ❗ Problem Statement

Cybersecurity data is frequently distributed across independent systems. User permissions, browsing logs, insider-threat indicators, and vulnerability records are often analyzed in isolation.

For example, an administrator visiting a potentially malicious website from a device with a critical vulnerability may represent a greater security risk than any of these signals considered individually.

The challenge is to integrate these scattered sources and use data mining techniques to identify risky combinations of events.

## ❓ Research Question

How can a unified cybersecurity lakehouse, built using a Bronze–Silver–Gold architecture, integrate user behavior, access permissions, website information, and endpoint vulnerabilities to support accurate and explainable cybersecurity risk assessment?

## 🏗️ Proposed System Architecture

### 1. Bronze Layer — Raw Data

The Bronze layer stores the original datasets with minimal transformation.

**Responsibilities:**
- Ingest raw cybersecurity datasets.
- Preserve original records for traceability.
- Record source information and ingestion metadata.
- Support reproducible data processing.

### 2. Silver Layer — Cleaned and Integrated Data

The Silver layer transforms raw data into consistent and analysis-ready datasets.

**Responsibilities:**
- Handle missing values and duplicate records.
- Standardize data types and timestamps.
- Normalize relevant categorical values.
- Match records using available identifiers and time information.
- Validate data quality and document integration limitations.

### 3. Gold Layer — Analytical Data

The Gold layer contains business-ready datasets for cybersecurity analysis.

**Responsibilities:**
- Build fact and dimension tables using a Star Schema.
- Combine relevant user activity, permission, website, and vulnerability indicators.
- Calculate analytical features for risk assessment.
- Prepare aggregated data for reports and dashboards.

## 🔎 Proposed Data Mining Techniques

### Anomaly Detection

Identify unusual browsing patterns, abnormal activity, or deviations from expected user behavior.

### Risk Scoring

Combine relevant security indicators into a risk score. Potential factors include:

- User privilege level.
- Website safety indicators.
- Endpoint vulnerability severity.
- Unusual user behavior.

The scoring method and weights should be documented and validated. A numerical risk score is an indicator for investigation, not proof of malicious activity.

### Risk Classification

Where suitable labeled examples are available, classify activities into categories such as low, medium, and high risk.

## 📊 Datasets

The project uses publicly available datasets and a proposed synthetic dataset for user access permissions.

| Dataset | Purpose | Source |
|---|---|---|
| CERT Insider Threat Dataset | Analyze insider-threat indicators and user behavior | [Kaggle](https://www.kaggle.com/datasets/andrihjonior/cert-insider-threat-dataset-r4-2) |
| CVE 2024 Database, Exploits, CVSS and OS | Analyze known vulnerabilities and severity indicators | [Kaggle](https://www.kaggle.com/datasets/manavkhambhayata/cve-2024-database-exploits-cvss-os) |
| Website URL with Industry | Analyze website-related information and potential browsing risk indicators | [Kaggle](https://www.kaggle.com/datasets/satyammishra0/website-url-with-industry) |
| Mock IAM & User Privilege Dataset | Represent user roles, departments, and permission levels | Synthetic dataset to be created for this project |

**Important:** The synthetic IAM dataset is intended to represent access-control information. Its records must be generated or documented separately; it should not be presented as an existing public dataset.

Dataset availability, licenses, schemas, and labels should be checked before use.

## 🛠️ Proposed Technologies

- **SQL:** Data cleaning, transformation, integration, and analytical queries.
- **Data warehouse:** Storage of structured and integrated cybersecurity data.
- **Medallion Architecture:** Organization of data into Bronze, Silver, and Gold layers.
- **Data mining / machine learning:** Anomaly detection, risk scoring, and classification.
- **Visualization:** Dashboards and charts for presenting cybersecurity risk indicators.

The final technology stack will depend on the tools selected during implementation.

## 📈 Expected Outcomes

- A unified analytical view of multiple cybersecurity data sources.
- Cleaned and integrated datasets organized into Medallion layers.
- Dimensional models suitable for analytical queries.
- Identification of potentially suspicious behavior and risky combinations of security indicators.
- Risk scores and risk categories, subject to implementation and validation.
- A foundation for future cybersecurity dashboards and monitoring systems.

## ⚠️ Limitations

- Public datasets may use different identifiers, timestamps, and schemas.
- Records from separate datasets may not describe the same real users or devices.
- Synthetic IAM records cannot establish real-world identity relationships.
- A combined risk score requires a documented methodology and evaluation.
- True real-time detection requires an implemented streaming or frequent-ingestion mechanism; batch analysis alone does not provide real-time monitoring.
- Anomaly detection results require further investigation and should not be treated as definitive evidence of an attack.

## 🚀 Project Status

**Current stage:** Proposed architecture and dataset selection.

Implementation status should be updated as the project progresses through data ingestion, transformation, dimensional modeling, data mining

