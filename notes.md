Started a project for market price optimization &rarr; 25.07.2023 Tuesday

* **Apache Spark (PySpark)** &rarr; Apache Spark is a multi-language engine for executing data engineering, data science, and machine learning on single-node machines or clusters.

    **Codes**

    ```
        sc = SparkContext()
    ``` 

    ```Python
        spark = SparkSession.builder.getOrCreate() 
        # This returns an existing SparkSession if there's already one in the environment, or creates a new one if necessary!
    ```

    ```Python
        spark.catalog.listTables()

        """
        Your SparkSession has an attribute called catalog which lists all the data inside the cluster. This attribute has a few methods for extracting different pieces of information.

        One of the most useful is the .listTables() method, which returns the names of all the tables in your cluster as a list.
        """
    ```

    ```Python
    # SQL Queries
    query = "SELECT * FROM TABLE"

    # Run SQL queries on spark data
    result = spark.sql(query)

    # Show the results
    result.show()
    ```

  * In practice, the cluster will be hosted on a remote machine that's connected to all other nodes. There will be one computer, called the _master_ that manages splitting up the data and the computations. The master is connected to the rest of the computers in the cluster, which are called _worker_. The master sends the workers data and calculations to run, and they send their results back to the master.
  * Spark's core data structure is _the Resilient Distributed Dataset (RDD)_. This is a low level object that lets Spark work its magic by splitting data across multiple nodes in the cluster. However, RDDs are hard to work with directly. So, we will be working with Spark DataFrame abstraction.
    * The Spark DataFrame was designed to behave a lot like a SQL table (a table with variables in the columns and observations in the rows). Not only are they easier to understand, DataFrames are also more optimized for complicated operations than RDDs.
    * When you start modifying and combining columns and rows of data, there are many ways to arrive at the same result, but some often take much longer than others. When using RDDs, it's up to the data scientist to figure out the right way to optimize the query, but the DataFrame implementation has much of this optimization built in!
    * To start working with Spark DataFrames, you first have to create a _SparkSession object from your SparkContext. You can think of the SparkContext as your connection to the cluster and the SparkSession as your interface with that connection.
  
  * [SparkContext()](https://spark.apache.org/docs/2.1.0/api/python/pyspark.html) Class ??
* **Hadoop** &rarr; Apache Hadoop is an open source framework that is used to efficiently store and process large datasets ranging in size from gigabytes to petabytes of data.
