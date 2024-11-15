# Databricks Notebook

## Configuration of cluster

### Libraries
- `h3==3.7.6`
- `psycopg2==2.9.10`

### Performance
- Databricks Runtime Version: `15.4 LTS (includes Apache Spark 3.5.0, Scala 2.12)`
- Worker & Driver type: `Standard_DS3_V2`
- Min workers=2, max workers=4
- Autoscaling & photon acceleration enabled
- Termination after a certain time enabled for good practice