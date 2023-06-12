![[spark_arch.png | 500]]
**Application** -> program built on spark. Consists of a **driver program** and **executors**
on the cluster.
**Driver program** -> process running main() function of the application and creating the SparkContext. The Deployment mode determines where the driver process runs. In cluster mode, the driver is inside the cluster. In client mode, the submitter launches the driver outside of the cluster.
**Executor** runs on Worker nodes. 
**Worker Node** -> node that can run application code on the cluster
**Task** -> Unit of work that will be sent to an executor
**Job** -> Parallel computation consisting of multiple tasks
**Stage** -> Each job gets divided into smaller sets of tasks called stages.