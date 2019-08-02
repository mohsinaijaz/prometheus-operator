# prometheus-operator

**Below we are going to install prometheus-operator using helm we will be deploying in AWS using Kops. Please refer to my K8-Kops repo to setup Kops on AWS**

**Prometheus-operator with helm is pretty much packaged to work out of the box, You can still modify from a wide range of options, we will create a values file with 2 options. Please look at kube-prometheus.yml for the changes we are making.**

**Make sure to have a working cluster with helm setup, refer to my Jenkins-on-Kubernetes for setting up helm**

**First start from downloading the chart for prometheus-operator and look at all the options that can be set.**

$ helm inspect stable/prometheus-operator > /tmp/prometheus-operator.yml

**I created a new file called kube-prometheus.yml which I specify NodePort for prometheus and grafana service and also credentials for grafana.**

$ helm install --name my-prometheus stable/prometheus-operator -f kube-prometheus.yml

**Once deployed look at at the pods and services**

$ kubectl get pods

$ kubectl get svc

**Make sure that our security groups is open to allow the NodePort 30000 t0 32000**
