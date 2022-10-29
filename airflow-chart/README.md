
https://airflow.apache.org/docs/helm-chart/stable/index.html <br />
https://airflow.apache.org/docs/apache-airflow/stable/howto/set-up-database. <br />html#setting-up-a-postgresql-database <br />
https://airflow.apache.org/docs/helm-chart/stable/parameters-ref.html <br />


➜ helm repo add apache-airflow https://airflow.apache.org <br />
➜ helm search repo  apache-airflow <br />
➜ helm fetch --version 1.7.0 apache-airflow/airflow <br />

➜ helm template . --name-template airflow -f values.yaml --output-dir '/Users/luis.costa/projects/stuff/batatas/➜ yamls'

or 

➜ helm template . --name-template airflow -n airflow -f values.yaml > ~/projects/stuff/eks/airflow.yaml<br />
➜ kubectl apply --namespace airflow -f /Users/luis.costa/projects/stuff/eks/airflow-chart/airflow.yaml

serviceaccount/airflow-create-user-job unchanged
serviceaccount/airflow-migrate-database-job unchanged
serviceaccount/airflow-redis unchanged
serviceaccount/airflow-scheduler unchanged
serviceaccount/airflow-statsd unchanged
serviceaccount/airflow-triggerer unchanged
serviceaccount/airflow-webserver unchanged
serviceaccount/airflow-worker unchanged
secret/airflow-postgresql created
secret/airflow-airflow-metadata unchanged
secret/airflow-webserver-secret-key unchanged
configmap/airflow-airflow-config configured
configmap/airflow-statsd unchanged
role.rbac.authorization.k8s.io/airflow-pod-launcher-role created
role.rbac.authorization.k8s.io/airflow-pod-log-reader-role created
rolebinding.rbac.authorization.k8s.io/airflow-pod-launcher-rolebinding created
rolebinding.rbac.authorization.k8s.io/airflow-pod-log-reader-rolebinding created
service/airflow-postgresql-headless created
service/airflow-postgresql created
service/airflow-redis unchanged
service/airflow-statsd unchanged
service/airflow-webserver unchanged
service/airflow-worker unchanged
deployment.apps/airflow-scheduler configured
deployment.apps/airflow-statsd configured
deployment.apps/airflow-triggerer configured
deployment.apps/airflow-webserver configured
statefulset.apps/airflow-postgresql created
statefulset.apps/airflow-redis configured
statefulset.apps/airflow-worker configured
secret/airflow-fernet-key unchanged
secret/airflow-redis-password unchanged
secret/airflow-broker-url unchanged
job.batch/airflow-create-user configured
job.batch/airflow-run-airflow-migrations configured



➜  kubectl get pods -n airflow    

NAME                                   READY   STATUS      RESTARTS        AGE
airflow-create-user-r885h              1/1     Running     0               5m52s
airflow-postgresql-0                   1/1     Running     0               8m36s
airflow-redis-0                        1/1     Running     0               16m
airflow-run-airflow-migrations-2nl4t   0/1     Completed   4               16m
airflow-scheduler-784c7cbd46-wmbff     2/2     Running     0               9m36s
airflow-statsd-5b4964646f-lqxpf        1/1     Running     1 (3m48s ago)   16m
airflow-triggerer-86658ddc4d-ggfch     1/1     Running     0               9m36s
airflow-webserver-677fc57bf4-g6fnh     0/1     Running     1 (76s ago)     16m
airflow-webserver-784f67cbdc-qsj6r     0/1     Running     1 (87s ago)     9m36s
airflow-worker-0                       2/2     Running     0               7m2s
