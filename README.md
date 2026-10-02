# 🛡️ ALSO Microsoft Security AI Security Policy Templates

>A comprehensive collection of Microsoft Security policy templates designed to help organizations securely adopt AI while reducing the risks associated with external third-party AI services, generative AI applications, browser-based AI tools, and local AI tools and agents running on Windows 11 endpoints.

**Works with Microsoft 365 Business Premium + Defender Suite + Purview Suite and up.**

> [!IMPORTANT]
> **⚠️ IMPORTANT: This solution works only on corporate owned Windows 11 devices.**
---

> [!IMPORTANT]
> **⚠️ IMPORTANT: Read this before importing and using any policies.**

| Resource | Description |
|-----------|-------------|
| 🛡️ **Security Information** | [View Security Policy](https://github.com/CoC-MS/ALSO-Microsoft-Security-WindowsServer?tab=security-ov-file) |
| 📖 **Supported and Unsupported OS and Scenarios** | [View description](https://github.com/CoC-MS/ALSO-Microsoft-Security-WindowsServer?tab=readme-ov-file#supported-and-unsupported-operating-systems-and-scenarios) |
| 📖 **Supported licenses** | [View description](https://github.com/CoC-MS/ALSO-Microsoft-Security-WindowsServer?tab=readme-ov-file#works-with-following-licenses) |
| 📖 **Before importing ALSO_WINDOWSSERVER_POLICIES** | [View description](https://github.com/CoC-MS/ALSO-Microsoft-Security-WindowsServer?tab=readme-ov-file#before-importing-also_windowsserver_policies) |

----


## 📂 File Structure

All files are organized into categories

```text
/ALSO-Microsoft-Security-WindowsServer
├── ALSO_WINDOWSSERVER_POLICIES/SettingsCatalog
3 SettingsCatalog policies


```

### Works with following licenses

| Tag | Minimum Required License |
|:---:|--------------------------|
| **BP** | Microsoft 365 Business Premium + Defender for Business for Servers -on-premises servers only (can't have mixed licensing with 2 others below |
| **E5** | Microsoft 365 E3 or Microsoft 365 E5 + Defender for Endpoint for Servers - on-premises servers only (can't have mixed licensing with 2 others above and below |
| **A365** | Defender for Servers P1 and P2 in Defender for Cloud - works with servers in Azure or Arc onboarded servers (can't have mixed licensing with 2 others above |

---

## 📖 Naming Convention

All policy templates follow the naming format below:

```text
<ALSO>-<ImpactLevel>-<MinimumLicense>-<BaselineLevel>-<Version>-<OS>-<Main Category>-<Sub Category>-<Settings>-<Assignment>
```

### Example

```text
ALSO – LI – MDBS – Basic – v1.0– WindowsServer – Endpoint Security - Antivirus - AV Configuration - D
```

---

## 🧩 Naming Components

| Component | Description |
|-----------|-------------|
| **ALSO** | Company providing the policy template to have a better control |
| **Impact** | Impact level of policy, low (LI), medium (MI) or high (HI) |
| **MinimumLicense** | Minimum Microsoft license required to use the policy |
| **BaselineLevel** | Baseline level of policy, Basic, Advanced |
| **Version** | Policy version, v1.0, v1.1 etc|
| **MacOS** | Operating system |
| **MainCategory** | Name of main category, Device Configuration, Device Compliance etc|
| **SubCategory** | Name of sub category, MDE, AV, Disk etc|
| **Settings** | Short settings description |
| **Assignment** | Assignment scope- device (D) or user (U)|


## Before importing ALSO_WINDOWSSERVER_POLICIES

## Prerequisites

Before importing **ALSO_WINDOWSSERVER_POLICIES**, ensure the following prerequisites are met:

## Requirements

-  **Microsoft Defender for Endpoint**
  - Microsoft Defender for Endpoint must be activated and configured in your tenant.

-  **Microsoft 365 Licensing**
  - Users must be assigned one of the following licenses:
    - Microsoft 365 Business Premium with Defender Suite
    - Microsoft 365 E3 with Defender Suite
    - Microsoft 365 E5
    - Microsoft 365 E7

-  **Microsoft Intune**
  - Microsoft Intune must be configured as the Mobile Device Management (MDM) authority.

  intune.microsoft.com->Devices-> Enrollment -> Automatic Enrollment

  <img width="1115" height="807" alt="image" src="https://github.com/user-attachments/assets/ae1527dd-0e7f-46c0-b63e-18d8f24ec2db" />


-  **Microsoft Defender for Endpoint Integration**
  - In the Microsoft Defender portal, navigate to:

    Settings -> Endpoint 
    
  - Enable the **Microsoft Intune connection**.
<img width="1451" height="609" alt="image" src="https://github.com/user-attachments/assets/fed83e08-2029-4e95-9775-16d872e20bdc" />

  

-  **Microsoft Defender for Cloud Apps Integration**
  - In the Microsoft Defender portal, navigate to:
    
   Settings -> Endpoints 
   
  - Microsoft Defender for Cloud Apps (MDCA)

  <img width="1467" height="1081" alt="image" src="https://github.com/user-attachments/assets/018f04ec-5ab3-4577-9f39-41f53b1fca68" />


-  **Endpoint Features**
  - In the Microsoft Defender portal, navigate to:

    Settings -> Endpoints 

  - Ensure the following features are enabled:
    - Custom Network Indicators
    - Web Content Filtering

  <img width="1467" height="1006" alt="image" src="https://github.com/user-attachments/assets/cd132687-9069-42bc-97ee-285910286be8" />
  

---

# Importing the Policies

The policies contained in this repository are designed to be imported using **MickeM's Intune Management Tool**.

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


## Require phishing resistant MFA + compliant device on sign in with Conditional Access

## Issues?
Open issue here: https://github.com/CoC-MS/ALSO-Microsoft-Security-WindowsServer/issues 

