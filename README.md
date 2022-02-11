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
### Validate & Deployment using -confirm
```powershell
New-AzResourceGroupDeployment -Name testvm -ResourceGroupName arm-vscode -TemplateFile .\winvm-template.json -TemplateParameterFile .\winvm-template.parameters.json -Confirm
```
### Validate Deployment using Deployment Mode
```powershell
New-AzResourceGroupDeployment -Name testvm -ResourceGroupName arm-vscode -TemplateFile .\winvm-template.json -TemplateParameterFile .\winvm-template.parameters.json -WhatIf -Mode Complete
```
![#1589F0](https://via.placeholder.com/15/1589F0/000000?text=+) `Complete mode is risky Mode. Refer MSFT doc. before running that mode.`

### Blogs
- ARM FAQS
  https://docs.microsoft.com/en-us/azure/azure-resource-manager/templates/frequently-asked-questions
- ARM Template Function https://cogan.to/1c3

## Wiki
https://21bshwjt.github.io/azarm/
