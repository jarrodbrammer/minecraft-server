
# BLA Minecraft Server

The deployment, installation and administration of the BLA Minecraft Server.
This is being deployed using Hashicorp Terraform and hosted on Amazon Web Services (AWS)


## Install Valhelsia 6
Instructions for installing Valhesia can be found below.
1. Download Java 17 - [Java 17 Download](https://aka.ms/download-jdk/microsoft-jdk-17.0.12-windows-x64.msi)
2. Download Prism Launcher - [Prism Launcher Download](https://github.com/PrismLauncher/PrismLauncher/releases/download/8.4/PrismLauncher-Windows-MSVC-Setup-8.4.exe)
3. Open the Prism Launcher. At the top right link your Microsoft account associated with your Minecraft Account
    ![Alt text](images/Prism_Account_Link.png)
     - This will prompt you to log into your Microsoft Account;
     - Allow Prism access to your account when prompted.
     - Once complete, navigate back to the Prism launcher
4. Add an instance via the top left of the launcher. 
     - This will open a screen with a list on the left of different file hosts
     - Select CurseForge, search and download *Valhelsia 6*
     ![Alt text](images/Add_Valhelsia_Instance.png)
5. Once it’s downloaded; navigate to Settings > Java
     - Increase the max allocated RAM to a minimum requirement of 6GB (6144 MB) or 8GB depending on your devices RAM capacity.
     ![Alt text](images/Set_Java_Allocations.png)
     - Once set; close the settings window.
6. Launch Valhelsia 6 from either the 'Launch' button or by double clicking on it.
     - This will initiate the install and launch process in order for you to play the game.
     - Follow this step each time you'd like to launch the modpack.

## Configure Server Access

Before configuring this, ensure you've had a user created by an administrator.
An email will be sent to you with the *SSO start URL* and *username* details.

1. Download AWS-CLI-V2 - [AWS CLI V2 Download](https://awscli.amazonaws.com/AWSCLIV2.msi)
     - Run the installer and wait for it to complete.
2. Open CMD and configure progromatic access via your AWS login

```powershell
  aws configure sso
```
3. This will prompt for the following details
```powershell
     $ aws configure sso
     SSO session name (Recommended): ServerUser
     SSO start URL [None]: ENTER_THE_SSO_START_URL_FROM_YOUR_EMAIL
     SSO region [None]: us-east-1
     SSO registration scopes [sso:account:access]: sso:account:access
```    
4. After completing the above details, you'll be prompted to confirm and login to your AWS account.
     - Once signed-in, fill out the remaining SSO details below:
```powershell
     CLI default client Region [None]: ap-southeast-4
     CLI default output format [None]: yaml
     CLI profile name [AdministratorAccess-${ACCOUNT_ID}]: ServerUser
```

5. Once complete, you'll be able to run CLI commands to switch the server on & off.
     - Take note of the profile name you've set, as you'll need it to login & run commands.


## Switching the Server On & Off.

1. Open the AWS CLI & Login
```powershell
     aws sso login --profile ${YOUR_CLI_PROFILE_NAME}
```
- You'll be prompted to sign into AWS
2. Switch the server on:
```powershell
     TBC
```
3. Switch the server off:
```powershell
     TBC
```