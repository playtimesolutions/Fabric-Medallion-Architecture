# Microsoft Fabric Medallion Architecture
A reference repository that you can use (copy to Azure DevOps) that follows the Medallion Architecture in Microsoft Fabric. You need to enable Git Integrations across multiple workspace to achieve this.

## Reference Architecture
![Production Ready Data Analytics Platform-Fabric drawio](https://github.com/playtimesolutions/Fabric-Medallion-Architecture/assets/19221213/60efe396-7ea6-4273-895d-87de573c5bc6)

This architecture diagram showcases how various Azure services can be combined to build an end-to-end data processing pipeline using the Microsoft Fabric platform.

## Source Layer

The Source layer includes:
- On-premises data warehouses using SQL Server
- Azure SQL databases (both serverless and provisioned)
- Unstructured data sources
- JSON/CSV files
- Relational databases

These represent the raw data sources that need to be ingested.

## Ingest Layer

In the Ingest layer:
- Azure Data Factory orchestrates the data ingestion from the sources
- Leverages Data Connectors to extract data from the various sources

## Process Layer

The Process layer is the core of the pipeline where the ingested raw data is transformed and enriched:

- Synapse Data Engineering workspaces are used for:
- Data transformation pipelines on the raw data using Synapse Pipelines and notebooks

The transformed and cleansed data is stored in a centralized Data Lake powered by Azure Storage

Synapse Spark pools and Azure Synapse Data Science workspaces enable:

- Advanced analytics
- Data science on the data in the lake

The processed data is stored in Synapse Data Warehouse which acts as the serving layer for BI and reporting

## Serve Layer
For Serving the data to end users and applications, the architecture uses:

- Semantic models in Power BI for self-service BI
- Real-time dashboards for operational reporting
- Integration with business apps like Power Apps

Azure AI services for:

- ML model hosting
- Serving predictions
- Enrichment of operational stores and systems

## Platform Enablers

Platform Enablers are leveraged:

- Azure Purview for data governance
- Microsoft Fabric for end-to-end integration

This reference architecture showcases how Microsoft Fabric can be used to build a comprehensive data platform that can:

- Ingest data from diverse sources
- Process and analyze it at scale
- Serve insights to end users and applications
- Ensure data governance and security

