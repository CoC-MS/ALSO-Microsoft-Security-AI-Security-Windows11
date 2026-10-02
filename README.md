# 🛡️ ALSO Microsoft Security AI Security Windows 11 Policy Templates

>This baseline delivers a hardened Windows 11 configuration that minimizes the risk of unauthorized third-party AI access while maintaining a productive user experience. It restricts application installation and execution, enforces Microsoft Edge as the approved browser, blocks Microsoft Store and proxy bypass methods, limits access to non-Microsoft AI services, and requires compliant corporate-managed devices through Conditional Access policies. The baseline also includes Agent 365 Conditional Access controls for AI agent governance. Although designed as a high-security configuration, all settings can be customized to meet organizational requirements.

**Works with Microsoft 365 Business Premium + Defender Suite + Agent 365 (for Agent 365 policies) and up.**

> [!IMPORTANT]
> **⚠️ IMPORTANT: This solution works only on corporate owned Windows 11 devices.**
---

> [!IMPORTANT]
> **⚠️ IMPORTANT: Read this before importing and using any policies.**

| Resource | Description |
|-----------|-------------|
| 🛡️ **Security Information** | [View Security Policy](https://github.com/CoC-MS/ALSO-Microsoft-Security-AI-Security-Windows11/tree/main?tab=security-ov-file) |
| 📖 **Supported licenses** | [View description](https://github.com/CoC-MS/ALSO-Microsoft-Security-AI-Security-Windows11/blob/main/README.md#works-with-following-licenses) |
| 📖 **Before importing ALSO_WINDOWSSERVER_POLICIES** | [View description](https://github.com/CoC-MS/ALSO-Microsoft-Security-AI-Security-Windows11#before-importing-also_ai_security_policies) |

----


## 📂 File Structure

All files are organized into categories

```text
/ALSO-Microsoft-Security-WindowsServer
├── ALSO_AI_SECURITY_POLICIES/SettingsCatalog
12 SettingsCatalog policies
├── ALSO_AI_SECURITY_POLICIES/CompliancePolicies
4 Compliance policies
├── ALSO_AI_SECURITY_POLICIES/ConditionalAccess
7 Conditional Access policies
├── ALSO_AI_SECURITY_POLICIES/Groups
4 security groups for Conditional Access policies
├── ALSO_AI_SECURITY_POLICIES/NamedLocations
1 Named Location for Conditional Access policy

```

### Works with following licenses

 Minimum Required License |
|--------------------------|
 Microsoft 365 Business Premium + Defender for Suite + Agent 365 (for Agent 365 policies) |
 Microsoft 365 E3 + Defender Suite + Agent 365 (for Agent 365 policies) |
 Microsoft 365 E5 + Agent 365 (for Agent 365 policies)
 Microsoft 365 E7

---

## 📖 Naming Convention

All policy templates follow the naming format below:

```text
<ALSO>-<ImpactLevel>-<MinimumLicense>-<BaselineLevel>-<Version>-<OS>-<Main Category>-<Sub Category>-<Settings>-<Assignment>
```

### Example

```text
ALSO – LI – BP – Basic – v1.0– WindowsS – WDAC/Appcontrol - Trust apps from managed installer only - D
```

---

## 🧩 Naming Components Device policies 

| Component | Description |
|-----------|-------------|
| **ALSO** | Company providing the policy template to have a better control |
| **Impact** | Impact level of policy, low (LI), medium (MI) or high (HI) |
| **MinimumLicense** | Minimum Microsoft license required to use the policy |
| **BaselineLevel** | Baseline level of policy, Basic, Advanced |
| **Version** | Policy version, v1.0, v1.1 etc|
| **Windows** | Operating system |
| **MainCategory** | Name of main category, Device Configuration, Device Compliance etc|
| **SubCategory** | Name of sub category, MDE, AV, Disk etc|
| **Settings** | Short settings description |
| **Assignment** | Assignment scope- device (D) or user (U)|

## 🧩 Naming Components Conditional Access policies 

| Component | Description |
|-----------|-------------|
| **MinimumLicense** | Minimum Microsoft license required to use the policy |
| **ALSO** | Company providing the policy template to have a better control |
| **CA###** | Unique Conditional Access policy number |
| **Persona** | Target user persona |
| **Apps** | Applications targeted by the policy |
| **Platforms** | Platforms targeted by the policy |
| **AccessControls** | Determines whether access is granted or blocked |
| **SessionControls** | Controls enforced by the policy |


## Before importing ALSO_AI_SECURITY_POLICIES


# **Microsoft Intune setup**
  - Microsoft Intune must be configured as the Mobile Device Management (MDM) authority.

  intune.microsoft.com->Devices-> Enrollment -> Automatic Enrollment

  <img width="1115" height="807" alt="image" src="https://github.com/user-attachments/assets/ae1527dd-0e7f-46c0-b63e-18d8f24ec2db" />


#  **Microsoft Defender for Endpoint Integration**
  - In the Microsoft Defender portal, navigate to:

    Settings -> Endpoint 
    
  - Enable the **Microsoft Intune connection**.
<img width="1451" height="609" alt="image" src="https://github.com/user-attachments/assets/fed83e08-2029-4e95-9775-16d872e20bdc" />

  

 # **Microsoft Defender for Cloud Apps Integration**
  - In the Microsoft Defender portal, navigate to:
    
   Settings -> Endpoints 
   
  - Microsoft Defender for Cloud Apps (MDCA)

  <img width="1467" height="1081" alt="image" src="https://github.com/user-attachments/assets/018f04ec-5ab3-4577-9f39-41f53b1fca68" />

And Settings -> Cloud Apps --> Microsoft Defender for Endpoint

<img width="1415" height="822" alt="image" src="https://github.com/user-attachments/assets/d87e30ea-ced1-46e5-a815-ff1cb81ea8e0" />


#  **Endpoint Features**
  - In the Microsoft Defender portal, navigate to:

    Settings -> Endpoints 

  - Ensure the following features are enabled:
    - Custom Network Indicators
    - Web Content Filtering

  <img width="1467" height="1006" alt="image" src="https://github.com/user-attachments/assets/cd132687-9069-42bc-97ee-285910286be8" />
  

---

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

<img width="401" height="373" alt="image" src="https://github.com/user-attachments/assets/b4005205-abc8-4e9b-a8b0-d6f919f99c06" />

   
9. Choose SettingsCatalog, CompliancePolicies, Conditional Access, Named Locations and Authentication context in menu, remove everything else.

> [!IMPORTANT]
> **10. On Conditional Access state- SELECT OFF. Very important.**
 
Uncheck import assignments if you don't want to to import groups, named locations and authentication context. PS: Many policies will fail on import here.

10. Check results on your tenant and if something is missing in CMD window. 


## After import

# AppControl/WDAC

App Control Managed Installer policy can't be improted as .json and needs to be setup manually, set it up before deploying App Control policy to your devices. Remember to double check that IME - Intune Managed Extension is installed on device, before enforcing policy for AppControl otherwise it wouldn't work. If it's not installing IME extension with Installer policy, than try to deploy an WIN32 app from Intune first

Policy name: ALSO – HI – BP – Advanced – v1.0- Windows -WDAC/AppControl- Enable Intune Managed Extension as Managed installer

<img width="1170" height="712" alt="image" src="https://github.com/user-attachments/assets/39cc4df6-c872-4e45-9c98-88323cba8c4b" />


## Blocking access to all known Non-Microsoft AI Sites

Once Defender for Endpoint and Cloud App integration is setup and you have device group in Defender go to Cloud Apps-> Cloud Apps Catalog --> Select All Gen AI and other AI apps , exclude non MS apps by tagging NON MS apps as Microsoft and than create a filter like on last picture

<img width="1805" height="1231" alt="image" src="https://github.com/user-attachments/assets/5d4366ae-b55c-4725-afe9-8e8fc2e53c8d" />

<img width="744" height="349" alt="image" src="https://github.com/user-attachments/assets/2d662bf3-17ef-42c0-ba4f-17c7769b9785" />

Than choose Select ALl and Tag them as Unsanctioned and select Device Group

## Blocking all well known proxies

In Settings -> Endpoint -> Web Content Filtering create a pplicy to Block "Illegal software", Illegal Software category contains well known proxies
<img width="1225" height="1202" alt="image" src="https://github.com/user-attachments/assets/d924548f-3f52-46b5-9bbc-3d7c89c68900" />


## Blocking 3 party Teams apps

Go to https://admin.teams.microsoft.com/policies/manage-apps
Actions -> Org wide setings 
<img width="1667" height="555" alt="image" src="https://github.com/user-attachments/assets/931d6098-318d-4108-8069-eb5768cc732b" />

Choose this setting and save 

<img width="364" height="862" alt="image" src="https://github.com/user-attachments/assets/717d7b80-ca5c-4947-a349-a73ffe08cd32" />


## Require compliant device on sign in with Conditional Access


## BP-ALSO-CA205-Internals-AllApps-Windows-Grant-RequireCompliantDevice

Requires Windows devices to be compliant before internal users can access cloud applications. Remember to set compliance requirements in Intune for Windows first. Check Windows repo to find compliance templates for Windows. PS: Verify the included group(s) and/or add your custom groups which have all internals in it. ALSO- All Internals is added as an example. This group needs to be imported to Entra, otherwise policy will fail on import with following message:

```text
Failed to invoke MS Graph with URL https://graph.microsoft.com/beta/identity/conditionalAccess/policies (Request ID: df5ea509-9005-47d1-9d00-8852534700ac). Status code: BadRequest. Response message: The server could not process the request because it is malformed or incorrect. Exception: The remote server returned an error: (400) Bad Request
```

---

## BP-ALSO-CA204-Internals-AllApps-AnyPlatform-Block-UnknownPlatforms

Blocks internal users from signing in using unsupported or unrecognized device platforms. PS: Verify the included group(s) and/or add your custom groups which have all internals in it. ALSO- All Internals is added as an example. This group needs to be imported to Entra, otherwise policy will fail on import with following message:

```text
Failed to invoke MS Graph with URL https://graph.microsoft.com/beta/identity/conditionalAccess/policies (Request ID: df5ea509-9005-47d1-9d00-8852534700ac). Status code: BadRequest. Response message: The server could not process the request because it is malformed or incorrect. Exception: The remote server returned an error: (400) Bad Request


```

## Agent 365 Conditional Access policies

## 🤖 Agent Policies

> [!IMPORTANT]
> **All Agent policies (CA501-CA505) require an Agent 365 license to be assigned and Agent 365 portal onboarding to be completed before import. Otherwise, the policies will fail during import and display the following error message.**

```text
"Failed to invoke MS Graph with URL https://graph.microsoft.com/beta/identity/conditionalAccess/policies (Request ID: df32d38d-3943-4a55-bfbc-e1e892358ebb). Status code: BadRequest. Response message: The server could not process the request because it is malformed or incorrect. Exception: The remote server returned an error: (400) Bad Request."
```

### A365-ALSO-CA501-Agents-AllApps-AnyPlatform-Block-HighRiskAgent

Prevents agent identities from accessing tenant resources when Microsoft identifies the agent as having a high risk level

---

### A365-ALSO-CA502-Agents-AllAgentIdentities-AllAgentResources-Block-AllExceptSelected

Denies access for all agent identities by default. Only explicitly approved or excluded agents are permitted. Agent approval can also be managed through the Agent 365 portal 

---

### A365-ALSO-CA503-Agents-AllAgentUsers-Grant-RequireCompliantDevice

Restricts agent user access to devices that meet organizational compliance requirements.

---

### A365-ALSO-CA504-Agents-AllAgentUsers-AllResources-Block-RiskyAgents

Blocks agent users when Microsoft Entra ID Protection classifies the identity as medium or high risk.

---

### A365-ALSO-CA505-Agents-AllAgentUsers-AllResources-Grant-RequireCompliantNetWork

Allows agent user access only from locations connected through the Global Secure Access compliant network.


## Issues?

Open issue here: https://github.com/CoC-MS/ALSO-Microsoft-Security-AI-Security-Windows11/issues
