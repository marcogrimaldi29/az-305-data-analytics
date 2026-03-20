# 🗄️ AZ-305: Data & Analytics Services — Deep Dive

### Study Notes Repository — 2026 Edition

[![Deploy to GitHub Pages](https://github.com/marcogrimaldi29/az-305-data-analytics/actions/workflows/pages.yml/badge.svg)](https://github.com/marcogrimaldi29/az-305-data-analytics/actions/workflows/pages.yml)
[![GitHub Pages Live](https://img.shields.io/badge/GitHub%20Pages-Live-brightgreen?logo=github)](https://marcogrimaldi29.com/az-305-data-analytics/)
[![Personal Hub of Marco Grimaldi](https://img.shields.io/badge/Blog-marcogrimaldi29.com-blue?logo=rss)](https://marcogrimaldi29.com)
[![AZ-305 Main Notes](https://img.shields.io/badge/AZ--305-Main%20Notes-blue?logo=microsoftazure)](https://marcogrimaldi29.com/az-305-study-notes/)

> - 🎯 **Purpose:** Deep-dive study notes covering six Azure Data & Analytics services heavily tested in the **AZ-305: Designing Microsoft Azure Infrastructure Solutions** exam.
> - 📅 **Version:** 2026
> - ✍ **Author:** [Marco Grimaldi](https://www.linkedin.com/in/marco-grimaldi29/)
> - 🌐 **Published:** [🥽 AZ-305: Data & Analytics Services — Deep Dive](https://marcogrimaldi29.com/az-305-data-analytics/)
> - 🔗 **Companion repos:** [📘 AZ-305 Study Notes](https://marcogrimaldi29.com/az-305-study-notes/) · [🥽 AZ-305: Azure Compute Services — Deep Dive](https://marcogrimaldi29.com/az-305-compute/) · [🥽 AZ-305: Azure Messaging Services — Deep Dive](https://marcogrimaldi29.com/az-305-messaging/) · [🥽 AZ-305: Migration, HA & BCDR — Deep Dive](https://marcogrimaldi29.com/az-305-bcdr/)
· [📘 AZ-104 Study Notes](https://marcogrimaldi29.com/az-104-study-notes/) 

---

## 📋 Services Covered

| Service | Category | Key Use Case |
|---------|----------|--------------|
| 🛢️ **Azure SQL** | Relational Database | Fully managed relational DB — Database, Managed Instance, VM |
| 🔀 **Azure Data Factory** | Data Integration / ETL | Code-free & code-first pipelines to move and transform data at scale |
| 🔊 **Azure Stream Analytics** | Real-time Stream Processing | SQL-based real-time queries on event streams |
| 🏭 **Azure Synapse Analytics** | Unified Analytics Platform | Data warehousing + big-data analytics in one workspace |
| 🧱 **Azure Databricks** | Apache Spark Analytics | Collaborative Spark-based data engineering, ML, and streaming |
| 📡 **Azure IoT** | IoT Platform | Device connectivity, management, routing, and telemetry ingestion |

---

## 🗂️ Repository Structure

```
az-305-data-analytics/
├── README.md                        ← 📍 You are here
├── index.md                         ← Site home page
├── 01-azure-sql.md                  ← Azure SQL deep dive
├── 02-azure-data-factory.md         ← Azure Data Factory deep dive
├── 03-azure-stream-analytics.md     ← Azure Stream Analytics deep dive
├── 04-azure-synapse-analytics.md    ← Azure Synapse Analytics deep dive
├── 05-azure-databricks.md           ← Azure Databricks deep dive
├── 06-azure-iot.md                  ← Azure IoT deep dive
├── 07-feature-comparison.md         ← Side-by-side comparisons & decision tables
└── 08-exam-caveats-cheatsheet.md    ← Exam traps, decision tree, quick-fire facts
```

---

## 📚 Official Learning Resources

| Resource | Link |
|----------|------|
| 📄 Official AZ-305 Exam Page | [AZ-305 Exam](https://learn.microsoft.com/en-us/credentials/certifications/exams/az-305/) |
| 📋 Skills Measured / Study Guide | [Official Study Guide](https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/az-305) |
| 🛢️ Azure SQL Docs | [Azure SQL overview](https://learn.microsoft.com/en-us/azure/azure-sql/azure-sql-iaas-vs-paas-what-is-overview) |
| 🔀 Azure Data Factory Docs | [ADF overview](https://learn.microsoft.com/en-us/azure/data-factory/introduction) |
| 🔊 Azure Stream Analytics Docs | [Stream Analytics overview](https://learn.microsoft.com/en-us/azure/stream-analytics/stream-analytics-introduction) |
| 🏭 Synapse Analytics Docs | [Synapse overview](https://learn.microsoft.com/en-us/azure/synapse-analytics/overview-what-is) |
| 🧱 Azure Databricks Docs | [Databricks on Azure](https://learn.microsoft.com/en-us/azure/databricks/introduction/) |
| 📡 Azure IoT Hub Docs | [IoT Hub overview](https://learn.microsoft.com/en-us/azure/iot-hub/iot-concepts-and-iot-hub) |
| 🧪 Free Practice Assessment | [Practice Assessment](https://learn.microsoft.com/en-us/credentials/certifications/exams/az-305/practice/assessment?assessment-type=practice&assessmentId=15) |

---

## ✅ Key Study Tips for Data & Analytics Questions

- 🎯 Know the **three SQL deployment options** and the exact feature gates between them
- 🔄 Understand when **ADF vs Synapse Pipelines vs Databricks** is the right ETL tool
- 💰 Know **Synapse Serverless vs Dedicated** — the cost model difference is exam-critical
- 📐 Know **Stream Analytics windowing types** — Tumbling, Hopping, Sliding, Session
- ⚡ Understand the **IoT Hub tier limits** and when IoT Central replaces IoT Hub
- 🔐 Know **Databricks Unity Catalog** vs workspace-level security
- 📊 Memorise **SLA values** — scenario questions test availability math

---

## 🌐 Published Website

These notes are hosted on **GitHub Pages** and published as a searchable website:

👉 **[🥽 AZ-305: Data & Analytics Services — Deep Dive](https://marcogrimaldi29.com/az-305-data-analytics/)**

---

## ✍ About the Author

These notes are maintained by **[Marco Grimaldi](https://www.linkedin.com/in/marco-grimaldi29/)** — Cloud Consultant, Language Trainer & Lifelong Learner.

📍 **Find more content at [🌐 marcogrimaldi29.com](https://marcogrimaldi29.com)**

> The website is continuously updated and based on my personal study notes and experiences. If you have any feedback, suggestions, or corrections, feel free to [reach out](https://marcogrimaldi29.com/contact/)!

---

## 📈 Analytics

This site uses [Umami](https://umami.is/) for privacy-friendly analytics.

---

## © Credits & Acknowledgements

The [Just the Docs](https://github.com/just-the-docs/just-the-docs) theme is used for a clean, documentation-style layout. Licensed under [MIT](https://opensource.org/license/MIT).

Created with the help of AI. Model used: [Claude Sonnet 4.6](https://www.anthropic.com/news/claude-sonnet-4-6). The content has been reviewed and edited by the author for accuracy and clarity, but may contain errors. Always verify against the latest [Microsoft documentation](https://learn.microsoft.com/en-us/azure/).

> *Not affiliated with or endorsed by Microsoft.*