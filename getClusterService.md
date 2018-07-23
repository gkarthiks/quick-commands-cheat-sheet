```shell
for clusterclass in $(oc get clusterserviceclass -o json | jq -r '.items[] | select(.spec.externalName=="gitlab-ce") | .metadata.name '); do
  echo "Cluster Class ->  ${clusterclass}"
done
```
