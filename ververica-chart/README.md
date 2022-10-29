helm repo add ververica https://charts.ververica.com

helm search repo  ververica

NAME                            CHART VERSION   APP VERSION     DESCRIPTION                                       
ververica/ververica-platform    5.3.0           2.7.0           Ververica Platform is the enterprise stream


helm fetch --version 5.3.0 ververica/ververica-platform

helm template . --name-template vvp -f values.yaml > ~/projects/stuff/eks/ververica.yml

helm template . --name-template vvp -f values.yaml --output-dir './Users/luis.costa/projects/stuff/batatas/yamls'


➜ kubectl apply --namespace vvp -f /Users/luis.costa/projects/stuff/eks/ververica.yml

serviceaccount/vvp-ververica-platform created
configmap/vvp-ververica-platform-config created
persistentvolumeclaim/vvp-ververica-platform created
role.rbac.authorization.k8s.io/vvp-ververica-platform created
rolebinding.rbac.authorization.k8s.io/vvp-ververica-platform created
service/vvp-ververica-platform created
deployment.apps/vvp-ververica-platform created
