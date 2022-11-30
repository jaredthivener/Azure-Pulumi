Azure Synapse Workspace and Pools

Starting point for enterprise analytics solutions based on Azure Synapse.

Running the App

Create a new stack:

$ pulumi stack init dev
Create a Python virtualenv, activate it, and install dependencies:

This installs the dependent packages needed for our Pulumi program.

$ python3 -m venv venv
$ source venv/bin/activate
$ pip3 install -r requirements.txt

Login to Azure CLI (you will be prompted to do this during deployment if you forget this step):

$ az login
Set the Azure region location to use:

$ pulumi config set azure-native:location westus2
Set the user ID to grant access to (e.g., your current user):

$ pulumi config set userObjectId $(az ad signed-in-user show --query=objectId | tr -d '"')
Run pulumi up to preview and deploy changes:

$ pulumi up
Previewing changes:
...

Performing changes:
...
Resources:
    + 13 created

Duration: 10m53s
Navigate to https://web.azuresynapse.net and sign in to your new workspace.
