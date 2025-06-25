# Cumulative for the  Basic RDD Operations
<details><summary>Prerequisites and Learning Objectives</summary>

## Prerequisites

- Knowledge about how to create a RDD in Spark.

## Objectives

- To learn about different operations that can be applied on RDDs.

---
</details>
<details><summary>Description</summary>

## Description

- Two types of operations can be applied on RDDs: 
  - Transformation
  - Action 

## Transformation 

- Transformation operations are used in manipulating RDD data and returns new RDD. 

- Transformations are evaluated lazily means they are not executed until an action is performed on it. 

- Each transformation is connected logically with its parent RDD through lineage graph. 

- Transformations are of two types:
  - Narrow Transformation
  - Wide Transformation

**1. Narrow Transformation** 

- In narrow transformation, there is no data movement between RDD's partitions after an operation is applied on it. Examples of narrow transformations are map(), flatMap(), filter(), union(), mapPartition(), etc.


**2. Wide Transformation**

- Wide transformation results in movement of data between RDD's partitions after an operation is applied on it. Shuffling of data happens in wide transformation. Examples of wide transformations are groupByKey(), reduceByKey(), aggregateByKey(), join(), repartition(), etc. 


## Action

- Actions are the operations that return a non-RDD value when applied on RDD. The value of action gets stored in the driver program. Example of action operations are count(), collect(), first(), take(), etc.

---

</details>
<details><summary>Real World Application</summary>

</details>
<details><summary>Implementation</summary> 


> For Basic RDD operations Implementation, refer `Action` and `Transformation` module.
</details>
<details><summary>Summary</summary> 

## Summary

- Operations on RDD are of two types, Transformation and Action. Transformations are the operations that is used for manipulating the dataset and its return type is always a RDD. Action operations on the other hand are used for computing all the RDD at once after applying all the transformations. Their return type is always a non-rdd value. 

- Transformations can be categorized between narrow and wide transformation. Narrow transformations are those which do not result in shuffling of data whereas, wide transformations always result in shuffling of data over the network.

- Some examples of transformations are map(), filter(), groupByKey(), repartition(), etc. Some examples of actions are reduce(), collect(), take(), first(), etc.

---
</details>
<details><summary>Practice Questions</summary>

[Practice Questions](./Quiz.gift)</details>
