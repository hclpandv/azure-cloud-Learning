## Azure Management Tools and Authentication

1. #### [Azure Portal](https://portal.azure.com/) 
2. #### [Azure Cloud Shell](https://shell.azure.com/)
* Online Azure Shell  
* Both Powershell and Bash supported  
* Azure Module, Terraform already installed)   
3. #### Install Powershell Az Module (Powershell 5.1 required, can be installed on Powershell Core 6.x versions)  

```powershell
Install-Module -Name Az -AllowClobber -Scope CurrentUser
```


4. #### Install Azure CLI (Windows MSI based Install, Ubuntu apt based --- Issues with WSL)

```powershell
Invoke-WebRequest -Uri https://aka.ms/installazurecliwindows -OutFile .\AzureCLI.msi; Start-Process msiexec.exe -Wait -ArgumentList '/I AzureCLI.msi /quiet'
```

```bash
curl -sL https://aka.ms/InstallAzureCLIDeb | sudo bash
```

![image](https://user-images.githubusercontent.com/13016162/71341172-1a449d00-257f-11ea-84aa-3d0e17c102b7.png)


## Setting up Azure service principal with Azure CLI -- for third party, API access (User it for Terraform)

![image](https://user-images.githubusercontent.com/13016162/71341098-ed908580-257e-11ea-9ba7-375a65a7dbe9.png)


![image](https://user-images.githubusercontent.com/13016162/71341855-0f8b0780-2581-11ea-9f22-89e94dbd956a.png)
