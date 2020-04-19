# Launching-Dataproc-Jobs-with-Cloud-Composer
In this lab, I useD Google Cloud Composer to automate the transform and load steps of an ETL data pipeline. The pipeline created a Dataproc cluster, performed transformations on extracted data (via a Dataproc PySpark job), and then uploaded the results to BigQuery. Then I triggered this pipeline.
Cloud Composer workflows are comprised of DAGs (Directed Acyclic Graphs). I created my own DAG, including design considerations, as well as implementation details, to ensure that my prototype meets the requirements.

I built an Apache Airflow DAG that:

* Begin running when triggered from an on-prem POST request
* Spin up a Dataproc cluster
* Run a Pyspark job on cluster
* Tear down cluster when job completes
* Upload Pyspark output to BigQuery
* Remove any remaining intermediate files

![image](https://user-images.githubusercontent.com/46541929/79678035-117a7580-81c5-11ea-8664-d21225190f64.png)
