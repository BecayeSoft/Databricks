# Databricks

This is an introduction to Azure Databricks.

Repository structure:

- `Explore products.ipynb`: The notebook that contains the code.
- `Key Concepts.md`: Key concepts of Databricks.
- `Apache Spark.md`: An overview of Spark infrastructure, clusters and how to create them on Azure.

Azure Databricks is a scalable platform for data analytics in Microsoft Azure. You can use Azure Databricks to build highly scalable solutions for data science and engineering, machine learning, and SQL-based data analytics.

Pre-requisites:
- An active Azure subscription

## 1. Clone the repository

```bash
git clone https://github.com/BecayeSoft/Databricks
```

## Create a Databricks Workspace

### Option 1: Using the Azure Portal

- Create a Workspace: [Azure Databricks workspace](https://portal.azure.com/#view/HubsExtension/BrowseResource/resourceType/Microsoft.Databricks%2Fworkspaces)
- Select your workspace and click on `Launch Workspace` to open the Databricks workspace.

### Option 2: Using the Azure CLI

- Select the [>_] button to the right of the search bar at the top of the page to create a new Cloud Shell in the Azure portal
- Run the command below to create a resource group and a Databricks workspace

```bash
cd Databricks
./setup.ps1         # or setup.ps1 <your_region>
```

## Create a cluster

An Azure Databricks cluster is a set of computation resources and configurations on which you run workloads (e.g. machine learning).
In Azure Databricks, there is a distinction between clusters:
- All-purpose clusters: to analyze data collaboratively using interactive notebooks
- Job clusters: to run automated jobs.

Create a cluster by clicking on `New` > `Clusters` on the left menu, then choose the relevant configuration for your cluster.

If you plan to train Machine Learning models, you can use GPU-enabled clusters.

## Create a notebook

Create a notebook by clicking on `New` > `Notebook` on the left menu.

## Upload the data

1. Download the `products.csv` file from the `data` folder in this repository
2. In your notebook, from the File menu, select `Upload Data to DBFS`, then select the `products.csv` file you downloaded.
3. Next, copy the PySpark code to read the data.

You can read the data, display it and even create visualizations.
See the notebook for more details.

