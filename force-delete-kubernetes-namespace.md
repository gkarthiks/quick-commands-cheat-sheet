The below script will delete :muscle: the provided `namespace` within the `OpenShift` cluster. If the cluster needs authorization, need to send the `"Authorization: bearer token"`. That can be taken from running the 
`oc whoami -t` command.

This is more helpful when the `namespace` is under `finializers deadlock` situation. In this situation, the namespace will be in `Terminating` phase and will stuck there for ever. 
Even of `oc delete project <namespace>` will gives you below error :warning:.

> Error from server (Conflict): Operation cannot be fulfilled on namespaces "<namespace>": The system is ensuring all content is removed from this namespace. Upon completion, this namespace will automatically be purged by the system.

```
kubectl proxy
echo "Deleting the namespace <namespace>"
oc project <namespace>
oc delete --all all,secret,pvc > /dev/null
oc get ns <namespace> -o json > tempfile
sed -i '' '/"kubernetes"/d' ./tempfile
curl --silent -H "Content-Type: application/json" -X PUT --data-binary @tempfile http://127.0.0.1:8001/api/v1/namespaces/<namespace>/finalize
```

Now it's gone :rocket: :racehorse: :satisfied:
