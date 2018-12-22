### IBM Cloud Foundry's cli commands

Install: 
```bash
curl -sL https://ibm.biz/idt-installer | bash
```

Configure Env: 
```bash
ibmcloud api https://api.ng.bluemix.net
```


Command | Description
--------|------------
`ibmcloud login` | Logs in to the cloud portal with prompts for email and passd
`ibmcloud target --cf` | Sets the target environment
`ibmcloud target -o <value> -s <value>` | Sets the *organization* and *space*
`ibmcloud plugin list` | List of installed plugins for cli
`ibmcloud cr` | IBM Container registry cli command