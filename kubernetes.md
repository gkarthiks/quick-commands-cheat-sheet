### Kubernetes Commands

| Command | Description |
| --------| ----------- |
| `kubectl patch crd/<CRD_NAME> -p '{"metadata":{"finalizers":[]}}' --type=merge` | To delete the orphaned CRD (CustomResourceDefinition) |
| [Click here](https://github.com/gkarthiks/quick-commands-cheat-sheet/blob/master/force-delete-kubernetes-namespace.md) | Force delete namespace that stuck in finalizer issue | 
| `kubectl delete pod <pod_name> --now` **or** `kubectl delete pods <pod_name> --grace-period=0 --force` | To delete the POD immediately without waiting |
| `kubectl rollout status deployment/<deployment_name>`|Watches the deployment and logs all the status changes|
|`kubectl rollout undo deployment/<deployment_name>`|Rolls back the recent deployment|
| `kubectl get --raw /metrics \| grep apiserver_storage_objects` | How many things do I have in etcd
| `kubectl get --raw /metrics \| grep etcd.*.sum` | Is etcd being slow
| `oc patch pv/<pv_name>  --type json -p $'- op: remove\n  path: /spec/claimRef'` | To reclaim the PV after the pod is deleted <br/> <sup>*</sup> Give double space after the \n |
| `oc patch pvc <pvc_name> -p '{"spec":{"volumeName": <volume_name>}'` | To change the volume name in existing PVC |
| `kubectl patch function <function_name> -p '{"metadata":{"finalizers":[]}}' --type=merge` | If you have [Kubeless](https://kubeless.io) function deployed and function not getting deleted |
| `kubectl get {kind}.{version}.{group}` | Query the resources using its GVK(R)
