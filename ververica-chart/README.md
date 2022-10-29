➜ helm repo add ververica https://charts.ververica.com <br />
➜ helm search repo  ververica <br />

NAME                            CHART VERSION   APP VERSION <br />     DESCRIPTION                                       
ververica/ververica-platform    5.3.0           2.7.0           Ververica Platform is the enterprise stream


➜ helm fetch --version 5.3.0 ververica/ververica-platform <br />
➜ helm template . --name-template vvp -f values.yaml > ~/projects/stuff/eks/ververica.yml <br />
or<br />
➜ helm template . --name-template vvp -f values.yaml --output-dir './Users/luis.costa/projects/stuff/batatas/yamls'


➜ kubectl apply --namespace vvp -f /Users/luis.costa/projects/stuff/eks/ververica.yml <br />

serviceaccount/vvp-ververica-platform created <br />
configmap/vvp-ververica-platform-config created <br />
persistentvolumeclaim/vvp-ververica-platform created <br />
role.rbac.authorization.k8s.io/vvp-ververica-platform created <br />
rolebinding.rbac.authorization.k8s.io/vvp-ververica-platform created <br />
service/vvp-ververica-platform created <br />
deployment.apps/vvp-ververica-platform created <br />
