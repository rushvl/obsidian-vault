We're migrating the pipelines from Apache Nifi to Airflow
The main reason for this is Nifi is not built for big data and is not very optimized(runs on a jvm). In times of high load the nifi server crashes and the devops team has to restart it. Airflow is designed for big data and won't have these issues, removing the dependency on the devops team. And it will be hosted on AWS rather than a local server which hosts nifi.


Isssues

1. Certificate issue, MSK credentials not working. Used AML secret smth smth chatgpt this
2. finally certificate issue was solved, but all consumer polls only returned null. we copied the python script to s3