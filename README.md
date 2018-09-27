# k8s
Kubernetes/Helm configs for ReportPortal

**Do note that this is a Beta version**


This Helm project is created to setup ReportPortal with only one command.
The help chart is tested on Minikube and creates a fully working ReportPortal project

The chart installs all mandatory services to run ReportPortal

The Helm chart installation consist of the following .yaml files:

- A `Ingress` to access the UI
- A `values.yaml` which exposes a few of the configuration options in the
charts.
- A `templates/_helpers.tpl` file which contains helper templates.

    ```
        helm repo add stable https://kubernetes-charts.storage.googleapis.com/
        helm repo add incubator https://kubernetes-charts-incubator.storage.googleapis.com/
    ```


You can deploy this chart with `helm install ./<project folder>`.

Commando to create those folders:
- `minikube ssh`

Also make sure that the vm.max_map_count is setup
- `minikube ssh`
- `sudo sysctl -w vm.max_map_count=262144`

The url to reach ReportPortal is http://reportportal.k8.com
Make sure that the url is added in the host file and the ip is the K8 ip address
Example:
- `192.1.1.1	reportportal.k8.com`
