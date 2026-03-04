---
layout: home
title: Home
nav_order: 1
---

# 🗄️ AZ-305: Data & Analytics Services — Deep Dive
{: .no_toc }

**Study Notes & Exam Prep — 2026 Edition**
{: .fs-5 .fw-300 }

[![Deploy to GitHub Pages](https://github.com/marcogrimaldi29/az-305-data-analytics/actions/workflows/pages.yml/badge.svg)](https://github.com/marcogrimaldi29/az-305-data-analytics/actions/workflows/pages.yml)
[![Personal Hub](https://img.shields.io/badge/Blog-marcogrimaldi29.com-blue?logo=rss)](https://marcogrimaldi29.com)
[![AZ-305 Main Notes](https://img.shields.io/badge/AZ--305-Main%20Notes-blue?logo=microsoftazure)](https://marcogrimaldi29.com/az-305-study-notes/)

> 🎯 **Purpose:** Deep-dive study notes covering six Azure Data & Analytics services heavily tested in the **AZ-305: Designing Microsoft Azure Infrastructure Solutions** exam.
> 📅 **Version:** 2026
> ✍️ **Author:** [Marco Grimaldi](https://www.linkedin.com/in/marco-grimaldi29/)
> 🌐 **Published:** [marcogrimaldi29.com/az-305-data-analytics](https://marcogrimaldi29.com/az-305-data-analytics/)
> 🔗 **Companion repos:** [📘 AZ-305 Study Notes](https://marcogrimaldi29.com/az-305-study-notes/) · [🥽 AZ-305: Azure Messaging Services — Deep Dive](https://marcogrimaldi29.com/az-305-messaging/)

---

## 🗺️ What's in This Repository?

This companion repository to the [AZ-305 Study Notes](https://marcogrimaldi29.com/az-305-study-notes/) zooms into **Azure Data & Analytics** — a cluster of services spanning relational databases, data integration, real-time stream processing, big-data warehousing, unified analytics, and IoT ingestion.

| File | Coverage |
|------|----------|
| [🛢️ 01 — Azure SQL](01-azure-sql.md) | SQL Database, Managed Instance, SQL Server on VM — tiers, HA, Geo-replication, SKUs |
| [🔀 02 — Azure Data Factory](02-azure-data-factory.md) | Pipelines, datasets, linked services, IR types, triggers, monitoring |
| [⚡ 03 — Azure Stream Analytics](03-azure-stream-analytics.md) | Streaming jobs, windowing, inputs/outputs, scaling, compatibility |
| [🏭 04 — Azure Synapse Analytics](04-azure-synapse-analytics.md) | Dedicated/serverless SQL pools, Spark pools, pipelines, Link, Studio |
| [🔥 05 — Azure Databricks](05-azure-databricks.md) | Workspaces, clusters, Delta Lake, Unity Catalog, SKUs, security |
| [📡 06 — Azure IoT](06-azure-iot.md) | IoT Hub, IoT Central, DPS, Device Twins, routing, tiers |
| [📊 07 — Feature Comparison](07-feature-comparison.md) | Side-by-side tables: ETL vs streaming, SQL options, analytics layers |
| [🎯 08 — Exam Caveats & Cheatsheet](08-exam-caveats-cheatsheet.md) | Decision trees, exam traps, quick-fire numbers, final checklist |

---

## 🔑 Why Data & Analytics Matters for AZ-305

Data services surface across **all four exam domains**:

- **Domain 2 — Data Storage Solutions (25–30%):** Choosing between Azure SQL options; relational vs NoSQL; data warehouse vs data lake
- **Domain 4 — Infrastructure Solutions (30–35%):** IoT architecture, stream processing pipelines, analytics platform design
- **Business Continuity:** SQL Geo-replication, Synapse failover, IoT Hub failover
- **Well-Architected Framework:** Cost optimisation between Synapse serverless vs dedicated; right-sizing Databricks clusters

> ⚠️ The exam frequently presents **architecture scenarios** where multiple services overlap — knowing exactly when to use Stream Analytics vs Databricks vs Synapse, or SQL Database vs Managed Instance vs SQL on VM, is where marks are won or lost.

---

## ⚡ Quick Navigation

| I need to know… | Go to |
|-----------------|-------|
| SQL Database vs Managed Instance vs VM | [07 — Comparison § SQL Options](07-feature-comparison.md#sql-deployment-options) |
| ADF vs Synapse Pipelines vs Databricks for ETL | [07 — Comparison § ETL](07-feature-comparison.md#etl--data-integration) |
| Stream Analytics vs Event Hubs vs Databricks Streaming | [07 — Comparison § Streaming](07-feature-comparison.md#real-time-streaming) |
| IoT Hub vs IoT Central vs Event Hubs | [07 — Comparison § IoT](07-feature-comparison.md#iot-ingestion) |
| All exam traps in one place | [08 — Exam Caveats](08-exam-caveats-cheatsheet.md) |
| Azure SQL HA & SLA options | [01 — Azure SQL § High Availability](01-azure-sql.md#high-availability) |
| Synapse Dedicated vs Serverless SQL pools | [04 — Synapse § SQL Pools](04-azure-synapse-analytics.md#sql-pools) |

---

*Not affiliated with or endorsed by Microsoft. Always verify against the latest [Microsoft documentation](https://learn.microsoft.com/en-us/azure/). Content is based on the [AZ-305 official study guide](https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/az-305).*
