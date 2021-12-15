# ado-az-cli-docker-demo

When using Azure CLI ADO Task, we can pass the authentication creds to the Az CLI Docker container can run az commands in the container.
When we use Azure CLI Task, it will use Service Connection and authentication with the Azure. It will also create a ENv var AZURE_CONFIG_DIR that will point to the $HOME/.azure folder which contains all the az cli creds files.
We can mount the  $HOME/.azure folder on the agent to the /root/.azure in the container and use the CLI commands.
```
docker run --rm -it -v $HOME/.azure:/root/.azure mcr.microsoft.com/azure-cli:2.31.0
```
