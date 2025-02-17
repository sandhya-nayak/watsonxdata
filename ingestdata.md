---

copyright:
  years: 2022, 2024
lastupdated: "2024-04-03"

keywords: watsonx.data, data ingestion, source file

subcollection: watsonxdata

---

{:javascript: #javascript .ph data-hd-programlang='javascript'}
{:java: #java .ph data-hd-programlang='java'}
{:ruby: #ruby .ph data-hd-programlang='ruby'}
{:php: #php .ph data-hd-programlang='php'}
{:python: #python .ph data-hd-programlang='python'}
{:external: target="_blank" .external}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:important: .important}
{:note: .note}
{:deprecated: .deprecated}
{:pre: .pre}
{:video: .video}

# About data ingestion
{: #load_ingest_data}

Data ingestion is the process of importing and loading data into {{site.data.keyword.lakehouse_full}}. You can use the **Create table** option from the **Data manager** page to load local or external sources of data files to create tables.
{: shortdesc}

When you ingest a data file into the {{site.data.keyword.lakehouse_short}}, the table schema is generated and inferred when a query is run.
Data ingestion in {{site.data.keyword.lakehouse_short}} supports CSV and Parquet formats. The files to be ingested must be of the same format type and same schema. {{site.data.keyword.lakehouse_short}} auto-discovers the schema based on the source file being ingested.

Following are some of the requirements or limitations of the **ibm-lh** tool:

* Schema evolution is not supported.
* Target table must be an iceberg format table.
* Partitioning is not supported.
* IBM Storage Ceph, IBM Cloud Object Storage (COS), AWS S3, and MinIO object storage are supported.
* `pathStyleAccess` property for object storage is not supported.
* Only Parquet and CSV file formats are supported as source data files.

## Loading or ingesting data through CLI
{: #load_ingest_datacli}

An ingestion job in {{site.data.keyword.lakehouse_short}} can be run with the **ibm-lh** tool. The tool must be pulled from the `ibm-lh-client` and installed in the local system to run the ingestion job through the CLI. For more details and instructions to install `ibm-lh-client` package and use the **ibm-lh** tool for ingestion, see [Installing ibm-lh-client](https://www.ibm.com/docs/en/watsonxdata/1.1.x?topic=package-installing-lh-client){: external} and [Setting up the ibm-lh command-line utility](https://www.ibm.com/docs/en/watsonxdata/1.1.x?topic=utilities-setting-up-lh-cli-utility){: external}.

The **ibm-lh** tool supports the following features:

- Auto-discovery of schema based on the source file or target table.
- Advanced table configuration options for the CSV files:

   * Delimiter
   * Header
   * File encoding
   * Line delimiter
   * Escape characters

- Ingestion of a single, multiple file(s), or a single folder (no sub folders) of S3 and local Parquet file(s).
- Ingestion of a single, multiple file(s), or a single folder (no sub folders) of S3 and local CSV file(s).
