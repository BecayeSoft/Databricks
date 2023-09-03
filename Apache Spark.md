# Apache Spark

## How does Spark work?

Spark uses clusters. \
Apache Spark clusters are groups of computers that are treated as a single computer. They enable processing of data to be parallelized across many computers to improve scale and performance. 

A cluster consists of a Spark *driver* and *worker nodes*. The **Driver Node** is the principal node. It determines the tasks to be assigned to **Worker Nodes**. The **Driver Node** sends work to the **Worker Nodes** and instructs them to pull data from a specified data source.

| In Databricks, the notebook interface is typically the driver program.

**Work** submitted to the cluster is divided into **Jobs**. **Jobs** are divided into **Tasks**. These **Tasks** represent a unit of work. 

The secret sauce of Spark's high performance is parallelism. Instead of scaling vertically (adding ressources to a single computer), it scales horizontally (adding more new nodes to the cluster as needed).

Spark parallelizes jobs at two levels:
- **Worker node**: on each worker node, there an **Executor**, a running Java virtual machine (JVM)
- **Slot**: Inside each **Executor** there are multiple **Slots**. A **Slot** is basically just a combination of a single (typically) CPU core and associated resources. This means that the number of **Slots** is dependent on the available cores on the working node. Each **Slot** executes one **Task** at a time.

- ![image](https://github.com/BecayeSoft/Databricks/assets/87549214/3a3df754-73a7-448a-a29b-92a6caf281fe)

## Creating a Spark Cluster

To create cluster, go to your workspaceand select `New` > `Cluster`:
![image](https://github.com/BecayeSoft/Databricks/assets/87549214/ab6d1d96-699f-4a7a-ba56-a62676b691d6)

When creating the cluster, you can specify configuration settings, including:

- A name for the cluster.
- A cluster mode, which can be:
  - High Concurrency: Suitable for workloads where multiple users will be using the cluster concurrently.
  - Standard: Suitable for single-user workloads that require multiple worker nodes.
  - Single Node: Suitable for small workloads or testing, where only a single worker node is required.
- The version of the Databricks Runtime to be used in the cluster; which dictates the version of Spark and individual components such as Python, Scala, and others that get installed.
- The type of virtual machine (VM) used for the worker nodes in the cluster.
- The minimum and maximum number of worker nodes in the cluster.
- The type of VM used for the driver node in the cluster.
- Whether the cluster supports autoscaling to dynamically resize the cluster.
- How long the cluster can remain idle before being shut down automatically.

## How does Azure manage cluster resources

When creating a cluster, you define VM types and other settings, but Azure Databricks handles the cluster's management. It uses Azure Kubernetes Service (AKS) for control and data planes, leveraging Azure's latest hardware for improved Spark performance. All cluster metadata is stored in an Azure Database with fault tolerance. You manage the cluster through the Azure Databricks UI, benefiting from features like auto-scaling and auto-termination.

![image](https://github.com/BecayeSoft/Databricks/assets/87549214/830e4116-bf08-4ff8-bd41-29cf63149a8b)
