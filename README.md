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

### Valivate Deployment using -whatif 

```powershell
New-AzResourceGroupDeployment -Name testvm -ResourceGroupName arm-vscode -TemplateFile .\winvm-template.json -TemplateParameterFile .\winvm-template.parameters.json -WhatIf -WhatIfResultFormat ResourceIdOnly
```

- New-AzResourceGroupDeployment -Name testvm -ResourceGroupName arm-vscode -TemplateFile .\winvm-template.json -TemplateParameterFile .\winvm-template.parameters.json -Confirm 
- New-AzResourceGroupDeployment -Name testvm -ResourceGroupName arm-vscode -TemplateFile .\winvm-template.json -TemplateParameterFile .\winvm-template.parameters.json -WhatIf -Mode Complete                    
- ARM FAQS
  https://docs.microsoft.com/en-us/azure/azure-resource-manager/templates/frequently-asked-questions
- ARM Template Function https://cogan.to/1c3
