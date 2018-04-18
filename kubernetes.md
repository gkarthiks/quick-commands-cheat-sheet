| Command | Description |
| --------| ----------- |
| To reclain the PV after the pod is deleted |  `oc patch pv/<pv_name>  --type json -p $'- op: remove\n  path: /spec/claimRef’` |
