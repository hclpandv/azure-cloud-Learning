[<<back](index.md)
## Azure Management Tools and Authentication

1. #### [Azure Portal](https://portal.azure.com/) 
2. #### [Azure Cloud Shell](https://shell.azure.com/)
Online Azure Shell  
Both Powershell and Bash supported  
Azure Module, git, ansible, Terraform already installed  

![image](https://user-images.githubusercontent.com/13016162/71394577-27719280-2638-11ea-8d98-d2aeec5bf498.png)

![image](https://user-images.githubusercontent.com/13016162/71394857-6e13bc80-2639-11ea-8de5-258a03d0f5f0.png)


3. #### Install Powershell Az Module (Powershell 5.1 required, can be installed on Powershell Core 6.x versions)  

```powershell
# Powershell
Install-Module -Name Az -AllowClobber -Scope CurrentUser
```


4. #### Install Azure CLI (Windows MSI based Install, Ubuntu apt based --- Issues with WSL)

```powershell
# Powershell
Invoke-WebRequest -Uri https://aka.ms/installazurecliwindows -OutFile .\AzureCLI.msi; Start-Process msiexec.exe -Wait -ArgumentList '/I AzureCLI.msi /quiet'
```

```bash
# bash
curl -sL https://aka.ms/InstallAzureCLIDeb | sudo bash
```

![image](https://user-images.githubusercontent.com/13016162/71341172-1a449d00-257f-11ea-84aa-3d0e17c102b7.png)


## Setting up Azure service principal with Azure CLI -- for third party, app access (Use it for Terraform)

>Automated tools that use Azure services should always have restricted permissions. Instead of having applications sign in as a fully privileged user, Azure offers service principals.
>
>An Azure service principal is an identity created for use with applications, hosted services, and automated tools to access Azure resources. This access is restricted by the roles assigned to the service principal, giving you control over which resources can be accessed and at which level. For security reasons, it's always recommended to use service principals with automated tools rather than allowing them to log in with a user identity.

```bash
# Create Service Principal with password string shown in output
az ad sp create-for-rbac --name ServicePrincipalName
# Create and assign your certificate
az ad sp create-for-rbac --name ServicePrincipalName --cert @/path/to/cert.pem
# Create sp and a new cert too (cab be stored in an azure vault)
az ad sp create-for-rbac --name vikisp --create-cert #----cert vikiSpCert --keyvault viki-vault
# Retrieve cert from vault
az keyvault secret show --name vikiSpCert --vault-name viki-vault
```
![image](https://user-images.githubusercontent.com/13016162/71341098-ed908580-257e-11ea-9ba7-375a65a7dbe9.png)

![image](https://user-images.githubusercontent.com/13016162/71341855-0f8b0780-2581-11ea-9f22-89e94dbd956a.png)

* Please keep your password and keys which you see in output safe as it can not be recovered in future
* However, you can reset it and get a new password/cert

```bash
az ad sp credential reset --name vikiServicePrincipal
```
Login using Service Principal

```bash
az login --service-principal -u <app-url> -p <password-or-cert> --tenant <tenant>
```
