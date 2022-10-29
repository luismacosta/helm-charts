
https://airflow.apache.org/docs/helm-chart/stable/index.html <br />
https://airflow.apache.org/docs/apache-airflow/stable/howto/set-up-database. <br 
https://airflow.apache.org/docs/apache-airflow/stable/howto/set-up-database#setting-up-a-postgresql-database <br />
https://airflow.apache.org/docs/helm-chart/stable/parameters-ref.html <br />


➜ helm repo add apache-airflow https://airflow.apache.org <br />
➜ helm search repo  apache-airflow <br />
➜ helm fetch --version 1.7.0 apache-airflow/airflow <br />

➜ helm template . --name-template airflow -f values.yaml --output-dir '/Users/luis.costa/projects/stuff/batatas/➜ yamls'

or 

➜ helm template . --name-template airflow -n airflow -f values.yaml > ~/projects/stuff/eks/airflow.yaml


➜ kubectl apply --namespace airflow -f /Users/luis.costa/projects/stuff/eks/airflow-chart/airflow.yaml

serviceaccount/airflow-create-user-job unchanged <br />
serviceaccount/airflow-migrate-database-job unchanged <br />
serviceaccount/airflow-redis unchanged <br />
serviceaccount/airflow-scheduler unchanged <br />
serviceaccount/airflow-statsd unchanged <br />
serviceaccount/airflow-triggerer unchanged <br />
serviceaccount/airflow-webserver unchanged <br />
serviceaccount/airflow-worker unchanged <br />
secret/airflow-postgresql created <br />
secret/airflow-airflow-metadata unchanged <br />
secret/airflow-webserver-secret-key unchanged <br />
configmap/airflow-airflow-config configured <br />
configmap/airflow-statsd unchanged <br />
role.rbac.authorization.k8s.io/airflow-pod-launcher-role created <br />
role.rbac.authorization.k8s.io/airflow-pod-log-reader-role created <br />
rolebinding.rbac.authorization.k8s.io/airflow-pod-launcher-rolebinding created <br />
rolebinding.rbac.authorization.k8s.io/airflow-pod-log-reader-rolebinding created <br />
service/airflow-postgresql-headless created <br />
service/airflow-postgresql created <br />
service/airflow-redis unchanged <br />
service/airflow-statsd unchanged <br />
service/airflow-webserver unchanged <br />
service/airflow-worker unchanged <br />
deployment.apps/airflow-scheduler configured <br />
deployment.apps/airflow-statsd configured <br />
deployment.apps/airflow-triggerer configured <br />
deployment.apps/airflow-webserver configured <br />
statefulset.apps/airflow-postgresql created <br />
statefulset.apps/airflow-redis configured <br />
statefulset.apps/airflow-worker configured <br />
secret/airflow-fernet-key unchanged <br />
secret/airflow-redis-password unchanged <br />
secret/airflow-broker-url unchanged <br />
job.batch/airflow-create-user configured <br />
job.batch/airflow-run-airflow-migrations configured <br />
<br />
<br />


➜  kubectl get pods -n airflow    

NAME                                   READY   STATUS      RESTARTS        AGE <br />
airflow-create-user-r885h              1/1     Running     0               5m52s <br />
airflow-postgresql-0                   1/1     Running     0               8m36s <br />
airflow-redis-0                        1/1     Running     0               16m <br />
airflow-run-airflow-migrations-2nl4t   0/1     Completed   4               16m <br />
airflow-scheduler-784c7cbd46-wmbff     2/2     Running     0               9m36s <br />
airflow-statsd-5b4964646f-lqxpf        1/1     Running     1 (3m48s ago)   16m <br />
airflow-triggerer-86658ddc4d-ggfch     1/1     Running     0               9m36s <br />
airflow-webserver-677fc57bf4-g6fnh     0/1     Running     1 (76s ago)     16m <br />
airflow-webserver-784f67cbdc-qsj6r     0/1     Running     1 (87s ago)     9m36s <br />
airflow-worker-0                       2/2     Running     0               7m2s <br />
