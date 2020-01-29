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

### Delete non-running pods
```shell
kubectl delete pods --field-selector=status.phase!=Running
```

### List the Pod's resources for containers and initContainers
```shell
kubectl get pod  -o go-template='{{"\n==================================================================\n"}}{{ range .items }}{{"Pod Name: "}}{{$podname := .metadata.name}}{{$podname}}{{"\n---------"}}{{ range .spec.containers}}{{"\n\tContainer Name: "}}{{ .name }}{{"\n\t---------------\n\t\tRequests: "}}{{ .resources.requests }}{{"\n\t\tLimits: "}}{{ .resources.limits }}{{"\n"}}{{ end }}{{ range .spec.initContainers}}{{"\n\tInitContainer Name:"}}{{.name}}{{"\n\t-------------------\n\t\tRequests: "}}{{ .resources.requests }}{{"\n\t\tLimits: "}}{{ .resources.limits }}{{"\n"}}{{ end }}{{"==================================================================\n\n"}}{{end}}'
```