

https://github.com/user-attachments/assets/84003286-8a8d-4675-83a2-1ec0567c69a8
The video shows the Windows repository, same logic applies to this

# 📥 How to import

[Public documentation](README.md)

Review [General prerequisites](general-prerequisites.md), [Windows 11 requirements](platform-and-ai-prerequisites.md), [Dependencies and import errors](dependencies-and-import-errors.md), and the selected package before starting.

# **Importing the Policies**

The policies contained in this repository are designed to be imported using **MickeM's Intune Management Tool**.


1. Download Micke M Intune Management Tool from here:  https://github.com/Micke-K/IntuneManagement
2. Extract folder and Start with start.cmd in the folder (works without local administrator rights on Windows and MacOS)
   <img width="635" height="247" alt="image" src="https://github.com/user-attachments/assets/ae7405c2-17cb-43a1-a96e-cd60181a2619" />

3. Command window and UI will open
4. Press on icon in upper right corner to sign in
   <img width="1311" height="965" alt="image" src="https://github.com/user-attachments/assets/2e835f79-5e07-4c7d-bd7c-5bd4976fde50" />

5. You may need a Global Administrator to consent to required API permissions first time if have not used these tool before. This can be done after sign-in by pressing same icon in upper right corner once more and press "Request Consent". Command Graph Command Line Tools application will be registered in Entra. Feel free to remove it after import or remove at least admin consent.

   <img width="294" height="145" alt="image" src="https://github.com/user-attachments/assets/675ebdc9-dc87-4633-bfa5-fbb92f7ba53d" />


6. After sign in and admin consent navigate to Bulk button in the left upper corner and press Import

   <img width="273" height="202" alt="image" src="https://github.com/user-attachments/assets/9e8b32ce-93fe-4ef8-9c19-325d138add8c" />

7. Download project and unzip folder

> [!IMPORTANT]
> **We highly recommend extracting the downloaded folder to a OneDrive location. Otherwise, some policies with long filenames may fail to extract.**

<img width="401" height="373" alt="image" src="https://github.com/user-attachments/assets/b4005205-abc8-4e9b-a8b0-d6f919f99c06" />


9. Choose SettingsCatalog, CompliancePolicies, Conditional Access, Named Locations and Authentication context in menu, remove everything else.

> [!IMPORTANT]
> **10. On Conditional Access state- SELECT OFF. Very important.**

Uncheck import assignments if you don't want to to import groups, named locations and authentication context. PS: Many policies will fail on import here.

10. Check results on your tenant and if something is missing in CMD window.

## After importing 

## IMPORTANT - AppControl 

App Control Managed Installer policy can't be improted as .json and needs to be setup manually, set it up before deploying App Control policy to your devices. Remember to double check that IME - Intune Managed Extension is installed on device, before enforcing policy for AppControl otherwise it wouldn't work. If it's not installing IME extension with Installer policy, than try to deploy an win32 app first

<img width="961" height="725" alt="image" src="https://github.com/user-attachments/assets/ff2e8d6c-fc16-470c-a6f0-ba99ba99d2e6" />

## Blocking All Non-Microsoft AI Sites

Once Defender for Endpoint and Cloud App integration is setup and you have device group in Defender go to Cloud Apps-> Cloud Apps Catalog --> Select All Gen AI and other AI apps , exclude non MS apps by tagging NON MS apps as Microsoft and than create a filter like on last picture

<img width="1805" height="1231" alt="image" src="https://github.com/user-attachments/assets/5d4366ae-b55c-4725-afe9-8e8fc2e53c8d" />

<img width="744" height="349" alt="image" src="https://github.com/user-attachments/assets/2d662bf3-17ef-42c0-ba4f-17c7769b9785" />

Than choose Select ALl and Tag them as Unsanctioned and select Device Group

## Blocking known proxies

In Settings -> Endpoint -> Web Content Filtering create a pplicy to Block "Illegal software", Illegal Software category contains well known proxies
<img width="1225" height="1202" alt="image" src="https://github.com/user-attachments/assets/d924548f-3f52-46b5-9bbc-3d7c89c68900" />


## Blocking 3 party Teams apps

Go to https://admin.teams.microsoft.com/policies/manage-apps
Actions -> Org wide setings 
<img width="1667" height="555" alt="image" src="https://github.com/user-attachments/assets/931d6098-318d-4108-8069-eb5768cc732b" />

Choose this setting and save 

<img width="364" height="862" alt="image" src="https://github.com/user-attachments/assets/717d7b80-ca5c-4947-a349-a73ffe08cd32" />


## Checking Copilot settings in Admin Center - if you are using Copilot today

1. Go to admin.microsoft.com -> Copilot -> Settings and set you restrictions for users. 

## Checking Agent 365 settings in Admin Center - if you have Agent 365 license 

1. Go to admin.microsoft.com -> Agents -> Settings -> Agent and plugin settings, User access and Sharing settings as minimum 

