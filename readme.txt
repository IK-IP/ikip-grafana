Grafana

microk8s helm repo add grafana https://grafana.github.io/helm-charts

microk8s helm repo update

microk8s helm install ikip-grafana grafana/grafana

microk8s helm status ikip-grafana

k get secret --namespace default ikip-grafana -o jsonpath="{.data.admin-password}" | base64 --decode ; echo

microk8s helm upgrade grafana grafana/grafana -f values.yaml

microk8s helm upgrade grafana grafana/grafana -f ikip-grafana-custom-values.yaml

k apply -f ingress_grafana.yaml

