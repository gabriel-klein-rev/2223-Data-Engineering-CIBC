# Azure Data Factory (ADF)

## ADF Overview
Azure Data Factory (ADF) is a cloud-based data integration service that enables creation, scheduling, and orchestration of data workflows (ETL/ELT). It allows movement and transformation of data from various sources to a centralized data store for analytics.

- Fully managed, serverless ETL service
- Connects to over 90+ data sources (on-prem and cloud)
- Enables data movement, transformation, and orchestration
- Integrates with Azure Synapse, Databricks, SQL, Blob Storage, etc.

---

## Data Factories
A data factory is a container that houses the ADF components used to define data workflows.

Components inside a data factory:
- **Pipelines**: Logical grouping of activities
- **Datasets**: References to data structures (e.g., a file or table)
- **Linked Services**: Connection strings to data sources or compute
- **Triggers**: Define when pipelines run (e.g., schedule, event-based)
- **Integration Runtimes**: Compute used to move and transform data

---

## Creating and Managing Data Factories
1. Go to the Azure portal.
2. Search and create a **Data Factory**.
3. Set region, name, and version.
4. Once created, launch **ADF Studio** to:
   - Author pipelines
   - Monitor executions
   - Manage data connections


---

## Data Ingestion Techniques
ADF supports various ingestion methods:

- **Copy Activity**: For structured and unstructured data
- **Binary Copy**: When no schema transformation is needed
- **Mapping Data Flows**: Visual transformations (drag-and-drop)
- **Wrangling Data Flows**: Power Query-based transformation
- **Custom activities**: Run custom scripts or external services

Ingestion can be:
- Batch (scheduled)
- Triggered (event or REST API)
- Hybrid (using self-hosted IR for on-prem sources)

---

## Building Data Pipelines
A pipeline is a set of **activities chained together** to perform a task.

Common activity types:
- **Copy Activity**: Move data from source to sink
- **Data Flow Activity**: Visually transform data
- **Databricks Notebook Activity**: Run notebooks as part of ETL
- **Lookup, If, Switch, ForEach**: Control flow activities

Steps:
1. Create datasets and linked services
2. Add activities and connect them
3. Parameterize for reusability
4. Validate and publish

---

## Monitoring Pipelines
ADF includes a built-in Monitor tab to:
- Track success/failure of pipeline runs
- View activity execution times
- Diagnose errors with logs
- Set up alerts using Azure Monitor or Log Analytics

Each run has a unique Run ID and detailed logs for troubleshooting.

---

## Connecting ADF to Databricks
ADF can invoke Azure Databricks notebooks via the Databricks Notebook activityda:

Steps:
1. Create a Linked Service to Databricks (access token or managed identity)
2. In the pipeline, add a Databricks Notebook activity
3. Select the workspace URL, cluster (or job cluster), and notebook path
4. (Optional) Pass parameters to the notebook

Use it to trigger:
- ELT transformations
- ML model training
- Delta Lake workflows

---

## Performance Optimization Techniques

- Use parallel copy by enabling multiple sink partitions
- Enable staging for large data loads (e.g., Blob → Synapse)
- Use filtering at the source when possible (avoid full loads)
- Use Data Flows with partitioning for large datasets
- Parameterize pipelines and reuse for scalability
- Monitor and tweak integration runtime scaling

## Resources

- https://learn.microsoft.com/en-us/azure/data-factory/quickstart-get-started

