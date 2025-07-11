# Structured Streaming Activity 2


## Objective

Practice working with structured streaming in Databricks using Notebooks.

## Instructions

### Sample Data 1

```
%fs ls /databricks-datasets/structured-streaming/events/
```

This sample data includes a directory of many JSON files. Each line in the JSON record contains two fields: *time* and *action*. Using structured streaming and setting maxFilesPerTrigger to 1, complete the following:

1. Ingest data by first creating input df

2. Transform input df to get total number of actions (per action type) per day

3. Start stream (fine to save to memory)

4. Query the result table to show the number of actions per type per day in order of day with most activity


### Sample Data 2

```
%fs ls /Volumes/workspace/w3d5/data/class_scores/
```

This data contains mock final scores for students across various classes stored as csv files. Each file has the same schema.

1. Create an input dataframe for this data to be streamed into. 

2. Transform the dataframe to include a rolling average score per class per semester

3. Start the stream and save output to a table in w3d5 schema with table name {name}_class_scores

4. Query the table using Databricks SQL to find the hardest class (by lowest score)

5. Determine if scores are different depending on which semester students took each class.