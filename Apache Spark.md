# Apache Spark

Apache Spark clusters are groups of computers that are treated as a single computer. 

Clusters enable processing of data to be parallelized across many computers to improve scale and performance. 

A cluster consists of a Spark *driver* and *worker nodes*. The **Driver Node** is the principal node. It determines the tasks to be assigned to **Worker Nodes**. The **Driver Node** sends work to the **Worker Nodes** and instructs them to pull data from a specified data source.

| In Databricks, the notebook interface is typically the driver program.

**Work** submitted to the cluster is divided into **Jobs**. **Jobs** are divided into **Tasks**. These **Tasks** represent a unit of work. 

The secret sauce of Spark's high performance is parallelism. Instead of scaling vertically (adding ressources to a single computer), it scales horizontally (adding more new nodes to the cluster as needed).

Spark parallelizes jobs at two levels:
- **Worker node**: on each worker node, there an **Executor**, a running Java virtual machine (JVM)
- **Slot**: Inside each **Executor** there are multiple **Slots**. A **Slot** is basically just a combination of a single (typically) CPU core and associated resources. This means that the number of **Slots** is dependent on the available cores on the working node. Each **Slot** executes one **Task** at a time.

- ![image](https://github.com/BecayeSoft/Databricks/assets/87549214/3a3df754-73a7-448a-a29b-92a6caf281fe)
