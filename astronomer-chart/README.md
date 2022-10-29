https://docs.astronomer.io/software <br />

➜ helm repo add astronomer https://helm.astronomer.io <br />
➜ helm search repo  astronomer <br />
NAME                            CHART VERSION   APP VERSION     DESCRIPTION <br />                                       
astronomer/astronomer           0.30.3          0.30.3          Helm chart to deploy the Astronomer Platform...<br />      
astronomer/airflow              1.7.1           2.0.0           Helm chart to deploy the Astronomer Platform Ai... <br />
astronomer/airflow-operator     0.4.0           0.4.0           2022-10-04T14:28:21+0000  https://circleci.com/... <br />
astronomer/alertmanager         0.11.0                          A Helm chart to deploy the Astronomer Platform ... <br />
astronomer/elasticsearch        0.11.0                          A Helm chart to deploy the Astronomer Platform ... <br />
astronomer/fluentd              0.11.0                          A Helm chart to deploy the Astronomer Platform ... <br />
astronomer/grafana              0.11.0                          Helm chart to deploy the Astronomer Platform Gr... <br />
astronomer/kibana               0.11.0                          Helm chart to deploy the Astronomer Kibana module  <br />
astronomer/kube-state           0.11.0                          A Helm chart to deploy the Astronomer Platform ... <br />
astronomer/nginx                0.11.0                          Helm chart to deploy the Astronomer Platform NG... <br />
astronomer/prometheus           0.11.0                          Helm chart to deploy the Astronomer Platform Pr... <br />

➜ helm fetch --version 0.30.3 astronomer/astronomer <br />
➜ helm template . --name-template astronomer -n astronomer -f values.yaml > ~/projects/stuff/eks/astronomer.yaml <br />

***Default*** <br />
➜ kubectl apply -n astronomer -f /Users/luis.costa/projects/stuff/eks/astronomer.yaml <br />

networkpolicy.networking.k8s.io/astronomer-alertmanager-policy created <br />
networkpolicy.networking.k8s.io/astronomer-astro-ui-policy created <br /> 
networkpolicy.networking.k8s.io/astronomer-cli-install-policy created <br />
networkpolicy.networking.k8s.io/astronomer-commander-policy created <br />
networkpolicy.networking.k8s.io/astronomer-houston-policy created <br />
networkpolicy.networking.k8s.io/astronomer-houston-worker-policy created <br />
networkpolicy.networking.k8s.io/astronomer-registry-policy created <br />
networkpolicy.networking.k8s.io/astronomer-elasticsearch-client-policy created <br />
networkpolicy.networking.k8s.io/astronomer-elasticsearch-data-policy created <br />
networkpolicy.networking.k8s.io/astronomer-elasticsearch-exporter-policy created <br />
networkpolicy.networking.k8s.io/astronomer-elasticsearch-master-policy created <br />
networkpolicy.networking.k8s.io/astronomer-elasticsearch-nginx-policy created <br />
networkpolicy.networking.k8s.io/astronomer-fluentd-policy created <br />
networkpolicy.networking.k8s.io/astronomer-grafana-policy created <br />
networkpolicy.networking.k8s.io/astronomer-kibana-policy created <br />
networkpolicy.networking.k8s.io/astronomer-kube-state-policy created <br />
networkpolicy.networking.k8s.io/astronomer-nats-policy created <br />
networkpolicy.networking.k8s.io/astronomer-nginx-default-backend-policy created <br />
networkpolicy.networking.k8s.io/astronomer-nginx-metrics-policy created <br />
networkpolicy.networking.k8s.io/astronomer-nginx-policy created <br />
networkpolicy.networking.k8s.io/astronomer-prometheus-policy created <br />
networkpolicy.networking.k8s.io/astronomer-stan-policy created <br />
networkpolicy.networking.k8s.io/astronomer-default-deny-ingress created <br />
Warning: policy/v1beta1 PodDisruptionBudget is deprecated in v1.21+, unavailable in v1.25+; use policy/v1 PodDisruptionBudget <br />
poddisruptionbudget.policy/astronomer-astro-ui-pdb created <br />
poddisruptionbudget.policy/astronomer-commander-pdb created <br />
poddisruptionbudget.policy/astronomer-houston-pdb created <br />
poddisruptionbudget.policy/astronomer-houston-worker-pdb created <br />
poddisruptionbudget.policy/astronomer-es-client-pdb created <br />
poddisruptionbudget.policy/astronomer-es-data-pdb created <br />
poddisruptionbudget.policy/astronomer-es-master-pdb created <br />
poddisruptionbudget.policy/astronomer-kibana-pdb created <br />
poddisruptionbudget.policy/astronomer-nats-pdb created <br />
poddisruptionbudget.policy/astronomer-nginx-default-backend-pdb created <br />
poddisruptionbudget.policy/astronomer-nginx-pdb created <br />
poddisruptionbudget.policy/astronomer-prometheus-pdb created <br />
poddisruptionbudget.policy/astronomer-stan-pdb created <br />
serviceaccount/astronomer-commander created <br />
serviceaccount/astronomer-config-syncer created <br />
serviceaccount/astronomer-houston-bootstrapper created <br />
serviceaccount/astronomer-elasticsearch created <br />
serviceaccount/astronomer-fluentd created <br />
serviceaccount/astronomer-grafana-bootstrapper created <br />
serviceaccount/astronomer-kube-state created <br />
serviceaccount/astronomer-nginx created <br />
serviceaccount/astronomer-prometheus-node-exporter created <br />
serviceaccount/astronomer-prometheus created <br />
secret/astronomer-houston-backend created <br />
secret/astronomer-registry-auth-key created <br />
secret/astronomer-grafana-backend created <br />
configmap/astronomer-alertmanager created <br />
configmap/astronomer-cli-install created <br />
configmap/astronomer-houston-config created <br />
configmap/astronomer-houston-worker-config created <br />
configmap/astronomer-elasticsearch-curator-config created <br />
configmap/astronomer-elasticsearch-config created <br />
configmap/astronomer-nginx-es created <br />
configmap/astronomer-fluentd created <br />
configmap/astronomer-grafana-datasource created <br />
configmap/astronomer-nats-config created <br />
configmap/astronomer-nginx-ingress-controller created <br />
configmap/astronomer-nginx-ingress-controller-headers created <br />
configmap/astronomer-prometheus-alerts created <br />
configmap/astronomer-prometheus-config created <br />
configmap/astronomer-stan-config created <br />
clusterrole.rbac.authorization.k8s.io/astronomer-commander created <br />
clusterrole.rbac.authorization.k8s.io/astronomer-config-syncer created <br />
clusterrole.rbac.authorization.k8s.io/astronomer-fluentd created <br />
clusterrole.rbac.authorization.k8s.io/astronomer-kube-state created <br />
clusterrole.rbac.authorization.k8s.io/astronomer-nginx created <br />
clusterrole.rbac.authorization.k8s.io/astronomer-prometheus created <br />
clusterrolebinding.rbac.authorization.k8s.io/astronomer-commander created <br />
clusterrolebinding.rbac.authorization.k8s.io/astronomer-config-syncer created <br />
clusterrolebinding.rbac.authorization.k8s.io/astronomer-fluentd created <br />
clusterrolebinding.rbac.authorization.k8s.io/astronomer-kube-state created <br />
clusterrolebinding.rbac.authorization.k8s.io/astronomer-nginx created <br />
clusterrolebinding.rbac.authorization.k8s.io/astronomer-prometheus created <br />
role.rbac.authorization.k8s.io/astronomer-houston-bootstrapper created <br />
role.rbac.authorization.k8s.io/astronomer-grafana-bootstrapper created <br />
role.rbac.authorization.k8s.io/astronomer-nginx-config created <br />
rolebinding.rbac.authorization.k8s.io/astronomer-houston-bootstrapper created <br />
rolebinding.rbac.authorization.k8s.io/astronomer-grafana-bootstrapper created <br />
rolebinding.rbac.authorization.k8s.io/astronomer-nginx-config created <br />
service/astronomer-alertmanager created <br />
service/astronomer-astro-ui created <br />
service/astronomer-cli-install created <br />
service/astronomer-commander created <br />
service/astronomer-houston created <br />
service/astronomer-elasticsearch created <br />
service/astronomer-elasticsearch-exporter created <br />
service/astronomer-elasticsearch-headless-discovery created <br />
service/astronomer-elasticsearch-nginx created <br />
service/astronomer-grafana created <br />
service/astronomer-kibana created <br />
service/astronomer-kube-state created <br />
service/astronomer-nats created <br />
service/astronomer-nginx-metrics created <br />
service/astronomer-nginx-default-backend created <br />
service/astronomer-nginx created <br />
service/astronomer-prometheus-node-exporter created <br />
service/astronomer-prometheus created <br />
service/astronomer-stan created <br />
daemonset.apps/astronomer-fluentd created <br />
daemonset.apps/astronomer-prometheus-node-exporter created <br />
deployment.apps/astronomer-astro-ui created <br />
deployment.apps/astronomer-cli-install created <br />
deployment.apps/astronomer-commander created <br />
deployment.apps/astronomer-houston created <br />
deployment.apps/astronomer-houston-worker created <br />
deployment.apps/astronomer-elasticsearch-client created <br />
deployment.apps/astronomer-elasticsearch-exporter created <br />
deployment.apps/astronomer-elasticsearch-nginx created <br />
deployment.apps/astronomer-grafana created <br />
deployment.apps/astronomer-kibana created <br />
deployment.apps/astronomer-kube-state created <br />
deployment.apps/astronomer-nginx-default-backend created <br />
deployment.apps/astronomer-nginx created <br />
statefulset.apps/astronomer-alertmanager created <br />
statefulset.apps/astronomer-elasticsearch-data created <br />
statefulset.apps/astronomer-elasticsearch-master created <br />
statefulset.apps/astronomer-nats created <br />
statefulset.apps/astronomer-prometheus created <br />
statefulset.apps/astronomer-stan created <br />
Warning: batch/v1beta1 CronJob is deprecated in v1.21+, unavailable in v1.25+; use batch/v1 CronJob <br />
cronjob.batch/astronomer-config-syncer created <br />
cronjob.batch/astronomer-houston-update-airflow-check created <br />
cronjob.batch/astronomer-houston-update-runtime-check created <br />
cronjob.batch/astronomer-houston-update-check created <br />
cronjob.batch/astronomer-houston-cleanup-deployments created <br />
cronjob.batch/astronomer-elasticsearch-curator created <br />
secret/astronomer-houston-jwt-signing-key created <br />
secret/astronomer-houston-jwt-signing-certificate created <br />
Warning: spec.template.spec.containers[0].env[7].name: duplicate name "DATABASE_URL" <br />
job.batch/astronomer-houston-db-migrations created <br />
job.batch/astronomer-houston-upgrade-deployments created <br />



***No logging + monitoring +  nodeExporter*** <br />
➜ kubectl apply -n astronomer -f /Users/luis.costa/projects/stuff/eks/astronomer.yaml <br />    

networkpolicy.networking.k8s.io/astronomer-astro-ui-policy created <br />
networkpolicy.networking.k8s.io/astronomer-cli-install-policy created <br />
networkpolicy.networking.k8s.io/astronomer-commander-policy created <br />
networkpolicy.networking.k8s.io/astronomer-houston-policy created <br />
networkpolicy.networking.k8s.io/astronomer-houston-worker-policy created <br />
networkpolicy.networking.k8s.io/astronomer-registry-policy created <br />
networkpolicy.networking.k8s.io/astronomer-nats-policy created <br />
networkpolicy.networking.k8s.io/astronomer-nginx-default-backend-policy created <br />
networkpolicy.networking.k8s.io/astronomer-nginx-metrics-policy created <br />
networkpolicy.networking.k8s.io/astronomer-nginx-policy created <br />
networkpolicy.networking.k8s.io/astronomer-stan-policy created <br />
networkpolicy.networking.k8s.io/astronomer-default-deny-ingress created <br />
Warning: policy/v1beta1 PodDisruptionBudget is deprecated in v1.21+, unavailable in v1.25+; use policy/v1 PodDisruptionBudget <br />
poddisruptionbudget.policy/astronomer-astro-ui-pdb created <br />
poddisruptionbudget.policy/astronomer-commander-pdb created <br />
poddisruptionbudget.policy/astronomer-houston-pdb created <br />
poddisruptionbudget.policy/astronomer-houston-worker-pdb created <br />
poddisruptionbudget.policy/astronomer-nats-pdb created <br />
poddisruptionbudget.policy/astronomer-nginx-default-backend-pdb created <br />
poddisruptionbudget.policy/astronomer-nginx-pdb created <br />
poddisruptionbudget.policy/astronomer-stan-pdb created <br />
serviceaccount/astronomer-commander created <br />
serviceaccount/astronomer-config-syncer created <br />
serviceaccount/astronomer-houston-bootstrapper created <br />
serviceaccount/astronomer-nginx created <br />
serviceaccount/astronomer-prometheus-node-exporter created <br />
secret/astronomer-houston-backend created <br />
secret/astronomer-registry-auth-key created <br />
configmap/astronomer-cli-install created <br />
configmap/astronomer-houston-config created <br />
configmap/astronomer-houston-worker-config created <br />
configmap/astronomer-nats-config created <br />
configmap/astronomer-nginx-ingress-controller created <br />
configmap/astronomer-nginx-ingress-controller-headers created <br />
configmap/astronomer-stan-config created <br />
clusterrole.rbac.authorization.k8s.io/astronomer-commander unchanged <br />
clusterrole.rbac.authorization.k8s.io/astronomer-config-syncer unchanged <br />
clusterrole.rbac.authorization.k8s.io/astronomer-nginx unchanged <br />
clusterrolebinding.rbac.authorization.k8s.io/astronomer-commander unchanged <br />
clusterrolebinding.rbac.authorization.k8s.io/astronomer-config-syncer unchanged <br />
clusterrolebinding.rbac.authorization.k8s.io/astronomer-nginx unchanged <br />
role.rbac.authorization.k8s.io/astronomer-houston-bootstrapper created <br />
role.rbac.authorization.k8s.io/astronomer-nginx-config created <br />
rolebinding.rbac.authorization.k8s.io/astronomer-houston-bootstrapper created <br />
rolebinding.rbac.authorization.k8s.io/astronomer-nginx-config created <br />
service/astronomer-astro-ui created <br />
service/astronomer-cli-install created <br />
service/astronomer-commander created <br />
service/astronomer-houston created <br />
service/astronomer-nats created <br />
service/astronomer-nginx-metrics created <br />
service/astronomer-nginx-default-backend created <br />
service/astronomer-nginx created <br />
service/astronomer-prometheus-node-exporter created <br />
service/astronomer-stan created <br />
daemonset.apps/astronomer-prometheus-node-exporter created <br />
deployment.apps/astronomer-astro-ui created <br />
deployment.apps/astronomer-cli-install created <br />
deployment.apps/astronomer-commander created <br />
deployment.apps/astronomer-houston created <br />
deployment.apps/astronomer-houston-worker created <br />
deployment.apps/astronomer-nginx-default-backend created <br />
deployment.apps/astronomer-nginx created <br />
statefulset.apps/astronomer-nats created <br />
statefulset.apps/astronomer-stan created <br />
Warning: batch/v1beta1 CronJob is deprecated in v1.21+, unavailable in v1.25+; use batch/v1 CronJob <br />
cronjob.batch/astronomer-config-syncer created <br />
cronjob.batch/astronomer-houston-update-airflow-check created <br />
cronjob.batch/astronomer-houston-update-runtime-check created <br />
cronjob.batch/astronomer-houston-update-check created <br />
cronjob.batch/astronomer-houston-cleanup-deployments created <br />
secret/astronomer-houston-jwt-signing-key created <br />
secret/astronomer-houston-jwt-signing-certificate created <br />
Warning: spec.template.spec.containers[0].env[7].name: duplicate name "DATABASE_URL" <br />
job.batch/astronomer-houston-db-migrations created <br />
job.batch/astronomer-houston-upgrade-deployments created <br />
