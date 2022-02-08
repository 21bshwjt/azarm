# Azure ARM Template

- New-AzResourceGroup -Name arm-vm-vscode -Location eastus
- New-AzResourceGroupDeployment -Name teststgARM -ResourceGroupName arm-vm-vscode -TemplateFile .\teststorage.json -TemplateParameterFile .\teststorage.param.json -Verbose
- Remove-AzResourceGroup -Name arm-vm-vscode -Verbose
- Test-AzResourceGroupDeployment -ResourceGroupName arm-vscode -TemplateFile .\azdeploy.json -TemplateParameterFile .\azdeploy.parameters.json -Verbose
- Export-AzResourceGroup -ResourceGroupName polaris00123 -Path .\ 
- ARM FAQS
  https://docs.microsoft.com/en-us/azure/azure-resource-manager/templates/frequently-asked-questions
