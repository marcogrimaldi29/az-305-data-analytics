---
layout: default
title: "02 — Azure Data Factory"
nav_order: 3
---

# 🔀 Azure Data Factory
{: .no_toc }

**Cloud-scale data integration service — code-free and code-first ETL/ELT pipelines**
{: .fs-5 .fw-300 }

---

## Table of Contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Product Overview

Azure Data Factory (ADF) is a **fully managed, serverless data integration and orchestration service**. It enables you to create data-driven workflows (pipelines) that orchestrate and automate data movement and transformation across on-premises, cloud, and SaaS sources.

ADF is the **primary ETL/ELT tool** in Azure, replacing the need for on-premises SSIS packages in most cloud architectures. It also serves as the orchestration layer for Azure Synapse Analytics workloads (Synapse Pipelines is ADF embedded in a Synapse workspace).

```mermaid
flowchart LR
    subgraph Sources["Data Sources"]
        ODB["On-premises DB\n(SQL, Oracle, SAP)"]
        SaaS["SaaS Apps\n(Salesforce, ServiceNow)"]
        Cloud["Cloud Stores\n(S3, GCS, REST APIs)"]
        Azure["Azure Services\n(Blob, ADLS, SQL)"]
    end
    subgraph ADF["Azure Data Factory"]
        LS["Linked Services\n(connection definitions)"]
        DS["Datasets\n(data shape + location)"]
        PL["Pipelines\n(workflow + orchestration)"]
        ACT["Activities\n(copy, transform, control)"]
        IR["Integration Runtime\n(execution engine)"]
        TRG["Triggers\n(schedule, event, tumbling)"]
    end
    subgraph Sinks["Destinations"]
        ADLS2["ADLS Gen2 / Blob"]
        SQLDW["Azure Synapse / SQL"]
        COSMOS["Cosmos DB"]
        EH["Event Hubs"]
    end
    Sources --> LS --> DS --> PL --> ACT --> IR --> Sinks
    TRG --> PL
```

---

## Core Concepts

### Linked Services
Connection definitions that store connection strings and credentials for data sources and sinks — analogous to ODBC DSNs. A linked service points to an external store or compute resource.

### Datasets
Named references to data within a linked service — they define the **structure, location, and format** of the data (e.g., a specific Blob container folder, a SQL table, a CSV schema).

### Activities
The steps inside a pipeline. ADF has three activity categories:

| Category | Examples |
|----------|---------|
| **Data movement** | Copy Activity (the main workhorse) |
| **Data transformation** | Data Flow, Databricks Notebook, HDInsight Hive, Stored Procedure, U-SQL |
| **Control flow** | ForEach, If Condition, Until, Wait, Execute Pipeline, Set Variable, Web Activity |

### Pipelines
A logical grouping of activities that together perform a unit of work. Pipelines support branching, looping, parallelism, and error handling via control flow activities.

### Integration Runtime (IR)
The execution infrastructure for ADF activities. This is one of the **most exam-tested concepts**.

| IR Type | Location | Use Case |
|---------|----------|----------|
| **Azure IR** | Azure (managed) | Cloud-to-cloud data movement and Data Flows; no setup required |
| **Self-hosted IR** | Customer premises or VM | Access on-premises or private-network data sources |
| **Azure-SSIS IR** | Azure (managed) | Lift-and-shift SSIS packages to run natively in ADF |

> ⚠️ **Exam Caveat — IR Type Selection:**
> - On-premises source → **Self-hosted IR** (installed on a machine that can reach the source)
> - Cloud-to-cloud → **Azure IR**
> - Migrating SSIS packages without rewriting → **Azure-SSIS IR**
> - Self-hosted IR can be **shared** across multiple ADF instances

### Triggers
Define when a pipeline runs:

| Trigger Type | Description |
|-------------|-------------|
| **Schedule** | Cron-based schedule (e.g., every day at 02:00 UTC) |
| **Tumbling Window** | Fixed, non-overlapping time slices; supports dependency chaining |
| **Storage Event** | Fires when a blob is created or deleted in Azure Blob/ADLS |
| **Custom Event** | Fires when a custom event arrives via Azure Event Grid |

> ⚠️ **Exam Caveat — Tumbling Window vs Schedule:** Tumbling Window triggers have **retry and dependency** features — they guarantee that each window is processed exactly once and in order. Schedule triggers do not have this guarantee. Use Tumbling Window for time-partitioned pipelines where **backfill and ordering** matter.

---

## Mapping Data Flows

**Mapping Data Flows** are visually designed, code-free transformations that run on **Azure Databricks Spark clusters** under the hood (fully managed by ADF, no cluster management needed). They support:

- Joins, aggregations, pivots, lookups, conditional splits
- Schema drift handling (dynamic schema evolution)
- Data quality and cleansing rules
- Debug mode for interactive testing

> ⚠️ **Exam Caveat:** Mapping Data Flows use **Spark as the execution engine** — they are not suitable for small datasets or latency-sensitive scenarios. They are designed for **batch transformations on large datasets**. For low-latency transformations, use a Stored Procedure activity or an Azure Function activity.

---

## Monitoring & Management

| Feature | Detail |
|---------|--------|
| **Monitor tab** | Visual pipeline run history, activity status, duration, errors |
| **Azure Monitor integration** | Pipeline metrics → Log Analytics, alerts on failure |
| **Diagnostic logs** | Activity runs, trigger runs, pipeline runs to Log Analytics |
| **Email alerts** | Configured via Azure Monitor action groups |
| **Git integration** | ADF supports GitHub or Azure DevOps Git for CI/CD of pipeline definitions |

---

## Security

| Feature | Detail |
|---------|--------|
| **Managed Identity** | Preferred for authenticating to Azure services without storing credentials |
| **Key Vault integration** | Linked service credentials stored in Key Vault; ADF fetches at runtime |
| **Managed VNet** | ADF managed virtual network for private connectivity to data sources |
| **Private Endpoints** | Managed private endpoints from ADF managed VNet to sources/sinks |
| **RBAC roles** | `Data Factory Contributor`, `Data Factory Operator` |
| **Encryption at rest** | AES-256; CMK supported via Key Vault |

---

## ADF vs Synapse Pipelines

| Aspect | Azure Data Factory | Synapse Pipelines |
|--------|-------------------|-------------------|
| **Location** | Standalone service | Embedded in Synapse workspace |
| **Feature parity** | Full feature set | Near-identical (shared codebase) |
| **Best for** | Standalone ETL, cross-workspace orchestration | ETL within a Synapse analytics project |
| **Licensing** | Separate resource | Included with Synapse workspace |
| **Integration** | Via linked services to Synapse | Native — pipelines can trigger Spark/SQL pool jobs directly |

> ⚠️ **Exam Caveat:** Synapse Pipelines and ADF share the **same underlying engine** — the exam treats them as functionally equivalent for integration scenarios. Choose Synapse Pipelines when the workload lives entirely inside a Synapse workspace; choose ADF for enterprise-wide, multi-platform integration.

---

## Pricing Model

| Component | Billing |
|-----------|---------|
| **Orchestration** | Per pipeline activity run (DIU-hours for Copy, vCore-hours for Data Flow) |
| **Copy Activity** | Per Data Integration Unit (DIU) hour |
| **Data Flow** | Per vCore-hour (cluster startup + execution time) |
| **Azure IR** | Per DIU-hour |
| **Self-hosted IR** | No ADF charge (customer pays for the VM) |
| **Azure-SSIS IR** | Per vCore-hour while running |

> ⚠️ **Exam Caveat:** Azure-SSIS IR is **billed per hour while running**, even if no packages execute. It should be **started just before SSIS package execution and stopped immediately after** to control costs.

---

## Common Exam Scenarios

| Scenario | Answer |
|----------|--------|
| Move data from on-premises Oracle to ADLS Gen2 | ADF pipeline with **Self-hosted IR** |
| Lift-and-shift existing SSIS packages to cloud | ADF with **Azure-SSIS IR** |
| Schedule-based batch ETL, cloud sources only | ADF pipeline with **Azure IR** + Schedule trigger |
| Trigger pipeline when a file lands in Blob storage | ADF **Storage Event trigger** |
| Code-free large-scale data transformation | ADF **Mapping Data Flow** |
| Store connection string securely in ADF | **Key Vault-backed Linked Service** |
| ETL within a Synapse Analytics workspace | **Synapse Pipelines** (same as ADF) |
| Incremental data load with time-window ordering | ADF **Tumbling Window trigger** |
| ADF pipeline credentials using managed identity | **Managed Identity** on ADF linked service |
