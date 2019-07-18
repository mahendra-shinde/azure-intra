## ARM Template demo

1. Visit https://github.com/azure

2. Click on link "Azure Quick Start Templates"
    It would open GitHub Repository for ARM Templates

3. Click on template with name "101-1vm-2nics-2subnets-1vnet" 

4. Download azuredeploy.json and azuredeploy.parameters.json files.

5. Open "azuredeploy.parameters.json" and provide username and password
    NOTE: GEN-UNIQUE and GEN-PASSWORD are Simply PLACE-HOLDERS
          Don't expect them to generate username or password

6. Open Powershell to login and create resource group

    ```pwsh
    $ Login-AzureRmAccount
    $ Get-AzureRmResourceGroup | select ResourceGroupName, Location
    $ New-AzureRmResourceGroup -Name rg1 -Location southeastasia
    ```
7.  Switch to directory where both JSON files are downloaded and create deployment

    ```pwsh
    ## Switch to directory which contains ARM template (JSON files)
    cd C:\Tech-Mahindra\demos\demo1

    ## Check if files exists!
    dir *.json

    New-AzureRmResourceGroupDeployment -Name deploy1 -ResourceGroupName rg1 `
        -TemplateFile .\azuredeploy.json -TemplateParameterFile .\azuredeploy.parameters.json

    ```

8.  Verify if VM is created !

    ```pwsh
    $ Get-AzureRmVM -ResourceGroupName rg1 | select Name
    ```
