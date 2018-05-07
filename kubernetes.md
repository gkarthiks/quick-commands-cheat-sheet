| Command | Description |
| --------| ----------- |
| To reclain the PV after the pod is deleted |  `oc patch pv/<pv_name>  --type json -p $'- op: remove\n  path: /spec/claimRef’` |
| To change the volume name in existing PVC | `oc patch pvc <pvc_name> -p '{"spec":{"volumeName": <volume_name>}'` |
| To delete the orphaned CRD (CustomResourceDefinition) | `kubectl patch crd/<CRD_NAME> -p '{"metadata":{"finalizers":[]}}' --type=merg`
