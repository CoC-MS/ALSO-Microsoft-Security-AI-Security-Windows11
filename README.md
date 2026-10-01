# 🛡️ ALSO Microsoft Security AI Security Policy Templates

>A comprehensive collection of Microsoft Security policy templates designed to help organizations securely adopt AI while reducing the risks associated with external third-party AI services, generative AI applications, browser-based AI tools, and local AI assistants running on endpoints.

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

## Supported and Unsupported Operating Systems and Scenarios

### ✅ Supported Operating Systems

| Operating System | Requirements |
|------------------|-------------|
| Windows Server 2012 R2 | Microsoft Defender for Down-Level Devices |
| Windows Server 2016 | Microsoft Defender for Down-Level Devices |
| Windows Server 2019 | KB5025229 installed |
| Windows Server 2019 Core | Server Core App Compatibility Feature on Demand installed |
| Windows Server 2022 | KB5025230 installed |
| Windows Server 2022 Core | KB5025230 installed |
| Windows Server 2025 | Supported |
| Domain Controllers | Supported. Review Microsoft documentation for important considerations before deployment. |

### ❌ Unsupported Operating Systems and Scenarios

| Operating System / Scenario | Status |
|----------------------------|--------|
| Windows Server Core 2016 and earlier | Not supported |
| Non-persistent desktops (VDI) | Not supported |
| Azure Virtual Desktop (AVD/WVD) | Not supported |
| 32-bit versions of Windows | Not supported |

> **Source:** Microsoft Learn  
> Full documentation is available here:  
> [Microsoft Defender Security Settings Management Documentation](https://learn.microsoft.com/en-us/intune/device-security/microsoft-defender/security-settings-management)


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
| **MDBS** | Microsoft 365 Business Premium + Defender for Business for Servers -on-premises servers only (can't have mixed licensing with 2 others below |
| **MDES** | Microsoft 365 E3 or Microsoft 365 E5 + Defender for Endpoint for Servers - on-premises servers only (can't have mixed licensing with 2 others above and below |
| **DFS** | Defender for Servers P1 and P2 in Defender for Cloud - works with servers in Azure or Arc onboarded servers (can't have mixed licensing with 2 others above |

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

| Requirement | Details |
|------------|---------|
| Licensing | Microsoft Defender for Business (MDB), Microsoft Defender for Endpoint Server (MDES), or Defender for Servers (DfS) licensing is required. |
| Operating System | Verify that your servers meet the minimum supported operating system requirements listed above. |
| Intune | Microsoft Intune must be deployed and actively used for device management. |
| Defender Services | Microsoft Defender for Endpoint and/or Microsoft Defender for Cloud must be enabled and configured in your tenant or subscriptions and all servers needs to be onboarded to Defender with status Onboarded and Active. |
| Permissions | You must have the **Security Administrator** and **Intune Administrator**  roles assigned. |

## Required Configuration 

1. Navigate to: security.microsoft.com -> Settings -> Endpoints -> Enforcement scope and toggle ON these settings for at least Windows Servers. Consider Domain Controllers. 

<img width="2061" height="1266" alt="image" src="https://github.com/user-attachments/assets/37e9ab7f-253e-419c-8f6c-b6b8e0cac383" />

2. Navigate to intune.microsoft.com -> Endpoint security > Microsoft Defender for Endpoint, and set Allow Microsoft Defender for Endpoint to enforce Endpoint Security Configurations to On.

<img width="1420" height="862" alt="image" src="https://github.com/user-attachments/assets/88068da1-754f-43d5-85ae-368c5e63b66b" />

> [!IMPORTANT]
> **⚠️IMPORTANT: Always double check official documentation here:** 

> **Source:** Microsoft Learn  
> Full documentation is available here:  
> [Microsoft Defender Security Settings Management Documentation](https://learn.microsoft.com/en-us/intune/device-security/microsoft-defender/security-settings-management)

## Create dynamic security groups in Entra for assignments

1. Create dynamic security group to catch your Windows Server devices

<img width="1731" height="715" alt="image" src="https://github.com/user-attachments/assets/149c3592-76dc-4f7e-9577-79d9fc9fda2f" />

To split it up in different OS groups, you need to add one more syntax with value for each policy you create. For example one for 2016, 2019 and so on. (Look at table below or in Entra ID -> Device -> Version) 

<img width="1713" height="740" alt="image" src="https://github.com/user-attachments/assets/ce9f2ff7-b263-4ce3-b03d-b8d1d92c6d93" />

## Windows Server Latest DeviceOSVersion Reference

| Windows Server | Release | DeviceOSVersion |
|---|---|---|
| Windows Server 2016 | 1607 | `10.0.14393` |
| Windows Server 2019 | 1809 | `10.0.17763` |
| Windows Server 2022 | 21H2 | `10.0.20348` |
| Windows Server 2025 | 24H2 | `10.0.26100` |

> [!IMPORTANT]
> **⚠️ IMPORTANT: Always double check Version coloumn value in Entra ID for your servers.**

-----
## How to import policy templates ALSO_WINDOWSSERVER_POLICIES 

1. Download Micke M Intune Management Tool from here:  https://github.com/Micke-K/IntuneManagement
2. Extract folder and Start with start.cmd in the folder (works without local administrator rights on Windows and MacOS)
   
   <img width="635" height="247" alt="image" src="https://github.com/user-attachments/assets/ae7405c2-17cb-43a1-a96e-cd60181a2619" />

4. Command window and UI will open
5. Press on icon in upper right corner to sign in

   <img width="1311" height="965" alt="image" src="https://github.com/user-attachments/assets/2e835f79-5e07-4c7d-bd7c-5bd4976fde50" />

6. You may need a Global Administrator to consent to required API permissions first time if have not used these tool before. This can be done after sign-in by pressing same icon in upper right corner once more and press "Request Consent". Command Graph Command Line Tools application will be registered in Entra. Feel free to remove it after import or remove at least admin consent.

   <img width="294" height="145" alt="image" src="https://github.com/user-attachments/assets/675ebdc9-dc87-4633-bfa5-fbb92f7ba53d" />


7. After sign in and admin consent navigate to Bulk button in the left upper corner and press Import

   <img width="273" height="202" alt="image" src="https://github.com/user-attachments/assets/9e8b32ce-93fe-4ef8-9c19-325d138add8c" />

8. Download ALSO_WINDOWSSERVER_POLICIES from this repo
9. Choose Bulk-> Import and find  folder
   
   <img width="391" height="411" alt="image" src="https://github.com/user-attachments/assets/e03b2025-83fd-45c0-9122-25f29fbb3e69" />
   
10. Check "Add Object name to path" and Press Import

   <img width="2256" height="861" alt="image" src="https://github.com/user-attachments/assets/ec182c21-9982-4f57-ae03-07022f66fbff" />

## Issues?
Open issue here: https://github.com/CoC-MS/ALSO-Microsoft-Security-WindowsServer/issues 

