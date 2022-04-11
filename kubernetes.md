### Kubernetes Commands

| Command | Description |
| --------| ----------- |
| To reclaim the PV after the pod is deleted |  `oc patch pv/<pv_name>  --type json -p $'- op: remove\n  path: /spec/claimRef'` <br/> <sup>*</sup> Give double space after the \n |
| To change the volume name in existing PVC | `oc patch pvc <pvc_name> -p '{"spec":{"volumeName": <volume_name>}'` |
| To delete the orphaned CRD (CustomResourceDefinition) | `kubectl patch crd/<CRD_NAME> -p '{"metadata":{"finalizers":[]}}' --type=merge`
| Force delete namespace that stuck in finalizer issue | [Click here](https://github.com/gkarthiks/quick-commands-cheat-sheet/blob/master/force-delete-kubernetes-namespace.md) |
| To delete the POD immediately without waiting | `kubectl delete pod <pod_name> --now` **or** `kubectl delete pods <pod_name> --grace-period=0 --force`|
| If you have [Kubeless](https://kubeless.io) function deployed and function not getting deleted | `kubectl patch function <function_name> -p '{"metadata":{"finalizers":[]}}' --type=merge`
|`kubectl rollout status deployment/<deployment_name>`|Watches the deployment and logs all the status changes|
|`kubectl rollout undo deployment/<deployment_name>`|Rolls back the recent deployment|
| `kubectl get --raw /metrics \| grep apiserver_storage_objects` | How many things do I have in etcd
| `kubectl get --raw /metrics \| grep etcd.*.sum` | Is etcd being slow
