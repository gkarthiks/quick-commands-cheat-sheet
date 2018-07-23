### Get ClusterServiceClass
```shell
for clusterclass in $(oc get clusterserviceclass -o json | jq -r '.items[] | select(.spec.externalName=="gitlab-ce") | .metadata.name '); do
  echo "Cluster Class ->  ${clusterclass}"
done
```


### Get ClusterRoleBinding
```sh
for result in $(oc get clusterrolebinding -o json | jq -r ".items[] | .groupNames | .[]"); do
  echo $result
done
```
