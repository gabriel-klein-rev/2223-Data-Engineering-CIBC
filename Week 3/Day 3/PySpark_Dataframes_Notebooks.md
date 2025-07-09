# PySpark - Spark SQL



### Drop duplicates


	data = [("Foo",41,"US",3),

		("Foo",39,"UK",1),

		("Bar",57,"CA",2),

		("Bar",72,"CA",2),

		("Baz",22,"US",6),

		("Baz",36,"US",6)]
  
  	data = spark.createDataFrame(data, ["x","y","z","count"])



	data.dropDuplicates(["x","count"]).show()


	data2 = spark.createDataFrame([(0, "hello"), (1, "world")] ,["id", "text"])

	from pyspark.sql.functions import col, udf
	from pyspark.sql.types import StringType


	upper = udf(lambda x: upper(x), StringType())

	data2.withColumn("upper", upper(col("text"))).show()

	dataFrame = spark.createDataFrame([("10.023", "75.0125", "00650"),("12.0246", "76.4586", "00650"), ("10.023", "75.0125", "00651")], ["lat","lng", "zip"])

	dataFrame.printSchema()

	dataFrame.select("*").where(dataFrame.zip == "00650").show()


### Join Operations in spark


	emp = [(1,"Smith",-1,"2018","10","M",3000),

		(2,"Rose",1,"2010","20","M",4000),

	 	(3,"Williams",1,"2010","10","M",1000),

		(4,"Jones",2,"2005","10","F",2000),

		(5,"Brown",2,"2010","40","",-1),

		(6,"Brown",2,"2010","50","",-1)

		]

	empColumns = ["emp_id","name","superior_emp_id","year_joined",
		"emp_dept_id","gender","salary"]
	  
	  
	empDF = spark.createDataFrame(emp, empColumns)

	empDF.show()

	dept = [("Finance",10),

		("Marketing",20),

		("Sales",30),

		("IT",40)

		]

	deptColumns = ["dept_name","dept_id"]

	deptDF = spark.createDataFrame(dept, deptColumns)

	deptDF.show()

	empDF.join(deptDF,empDF.emp_dept_id == deptDF.dept_id,"inner").show()

	empDF.join(deptDF,empDF.emp_dept_id == deptDF.dept_id,"outer").show()

	empDF.join(deptDF,empDF.emp_dept_id == deptDF.dept_id,"full").show()

	empDF.join(deptDF,empDF.emp_dept_id == deptDF.dept_id,"fullouter").show()



### Spark aggregate 


	simpleData = [("James","Sales","NY",90000,34,10000),

		("Michael","Sales","NY",86000,56,20000),

		("Robert","Sales","CA",81000,30,23000),

		("Maria","Finance","CA",90000,24,23000),

		("Raman","Finance","CA",99000,40,24000),

		("Scott","Finance","NY",83000,36,19000),

		("Jen","Finance","NY",79000,53,15000),

		("Jeff","Marketing","CA",80000,25,18000),

		("Kumar","Marketing","NY",91000,50,21000)

	]

	df = spark.createDataFrame(simpleData, ["employee_name","department","state","salary","age","bonus"])

	df.show()



	df.groupBy("department").count().show()

	df.groupBy("department").avg("salary").show()

	df.groupBy("department").sum("salary").show()

	df.groupBy("department").min("salary").show()

	df.groupBy("department").max("salary").show()

	df.groupBy("department").mean("salary").show()




	df.groupBy("department","state").sum("salary","bonus").show()

	df.groupBy("department","state").avg("salary","bonus").show()

	df.groupBy("department","state").max("salary","bonus").show()

	df.groupBy("department","state").min("salary","bonus").show()

	df.groupBy("department","state").mean("salary","bonus").show()

	df.groupBy("department","state").sum("salary","bonus").show()

	from pyspark.sql.functions import sum,avg,max,count

	df.groupBy("department").agg(sum("salary").alias("sum_salary"),avg("salary").alias("avg_salary"),sum("bonus").alias("sum_bonus"),max("bonus").alias("max_bonus")).show()


