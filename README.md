# Azure ARM Template

### Create Resource Group

```powershell
New-AzResourceGroup -Name arm-vm-vscode -Location eastus -Verbose
```
### Deploy Resource

```powershell
New-AzResourceGroupDeployment -Name teststgARM -ResourceGroupName arm-vm-vscode -TemplateFile .\teststorage.json -TemplateParameterFile .\teststorage.param.json -Verbose
```
### Remove Resource Group

```powershell
Remove-AzResourceGroup -Name arm-vm-vscode -Verbose
```
### Export Templete from Resource Group

```powershell
Export-AzResourceGroup -ResourceGroupName polaris00123 -Path .\ 
```

### Validate Deployment using -whatif 

```powershell
New-AzResourceGroupDeployment -Name testvm -ResourceGroupName arm-vscode -TemplateFile .\winvm-template.json -TemplateParameterFile .\winvm-template.parameters.json -WhatIf -WhatIfResultFormat ResourceIdOnly
```
### Validate Deployment using -whatif -PowerShell Spatting 

```powershell
$parameters = @{
    ResourceGroupName = "arm_storageacct3"
    templatefile = ".\azdeploy.json"
    templateparameterfile = ".\azdeploy.parameters.json"
    DeploymentName = "ARM_StorageAccountsDeploy"
    }
  
New-AzResourceGroupDeployment @parameters -WhatIf
```
### Validate & Deployment using -confirm
```powershell
New-AzResourceGroupDeployment -Name testvm -ResourceGroupName arm-vscode -TemplateFile .\winvm-template.json -TemplateParameterFile .\winvm-template.parameters.json -Confirm
```
### Validate Deployment using Deployment Mode
```powershell
New-AzResourceGroupDeployment -Name testvm -ResourceGroupName arm-vscode -TemplateFile .\winvm-template.json -TemplateParameterFile .\winvm-template.parameters.json -WhatIf -Mode Complete
```
```diff
- 'Complete' Mode is risky Mode. Refer MSFT kb before running that mode.
```
MSFT KB : https://docs.microsoft.com/en-us/azure/azure-resource-manager/templates/deployment-modes


### Blogs
- ARM FAQS
  https://docs.microsoft.com/en-us/azure/azure-resource-manager/templates/frequently-asked-questions
- ARM Template Function https://cogan.to/1c3

## Wiki
https://21bshwjt.github.io/azarm/


_______________________________________

### Deploy a VM to Azure using GitHub Actions
https://www.youtube.com/watch?v=0kDr9OlAzlM
