# 🚀 General prerequisites

[Public documentation](README.md)

Review these requirements before selecting a package. This solution is for corporate-owned Windows 11 devices, and every export requires tenant-specific review.

## Licensing

Use the [licensing guide in the main README](../../README.md#windows-11-ai-security-licensing-guide) and choose exactly one package:

- `ALSO_AI_SECURITY_WINDOWS11_BP` for the baseline artifacts without Agent 365 policies.
- `ALSO_AI_SECURITY_WINDOWS11_E7` for the cumulative package, including the five A365 Conditional Access policies.

Confirm current product names, feature availability, and entitlements with Microsoft before deployment. A policy filename is not proof that its required features are licensed in a tenant.

## Before importing ALSO_AI_SECURITY_POLICIES

# **Conditional Access setup**

For Conditional Access:

At least Conditional Access Administrator role assigned

> [!IMPORTANT]
> **Always import Conditional Access policies in OFF mode**:
> Ensure you have Conditional Access Administrator role before importing Conditional Access policies and that your Security defaults are turned off. To check if your tenant are using Security defaults use this direct link here:

Direct link: https://entra.microsoft.com/#view/Microsoft_AAD_IAM/TenantOverview.ReactView/initialValue//tabId//recommendationResourceId//fromNav/Identity

<img width="1559" height="197" alt="image" src="https://github.com/user-attachments/assets/b947568d-76d3-4a93-ae4a-5e293c68e59a" />

# **Local administrator settings**

Go to entra.microsoft.com -> Devices -> Device settings and check local administrator settings 

We reccomend these settings to be set and using LAPS for all local admin activitites across devices or EPM in Intune (requires Intune Suite or Microsoft 365 E5 to use EPM in Intune)

<img width="689" height="418" alt="image" src="https://github.com/user-attachments/assets/390114b9-d97e-49b6-8513-a0715409a62c" />

> [!IMPORTANT]
> **If you already have local administrators on devices today, you would need to remove those rights as well**

> **If you allow device registrations, you'll need to ensure you have control on those**

> **If you are using Autopilot only, you can handle local admin settings easy in your autopilot profile**

> **If you are using hybrid-joined, you can handle local admin rights with GP settings**

# **Agent 365 setup** only for E7 package

At least AI Administrator role 

1. Go to admin.microsoft.com -> Agents-> Overview and ensure your Agent 365 instance is active and in onbaorded state

Direct link: https://admin.cloud.microsoft/#/agents/overview

# **Microsoft Intune setup**

At least Intune Administrator role required 

  - Microsoft Intune must be configured as the Mobile Device Management (MDM) authority.

  intune.microsoft.com->Devices-> Enrollment -> Automatic Enrollment

  Direct link: https://intune.microsoft.com/#view/Microsoft_AAD_IAM/MdmConfiguration.ReactView/appId/0000000a-0000-0000-c000-000000000000/appName/Microsoft%20Intune

  <img width="1115" height="807" alt="image" src="https://github.com/user-attachments/assets/ae1527dd-0e7f-46c0-b63e-18d8f24ec2db" />



#  **Microsoft Defender for Endpoint/ Business Integration**

At least Security Administrator role required 

  - In the Microsoft Defender portal, navigate to:

    Settings -> Endpoint

  - Enable the **Microsoft Intune connection**.

Direct link: https://security.microsoft.com/securitysettings/endpoints/integration?tid

<img width="1451" height="609" alt="image" src="https://github.com/user-attachments/assets/fed83e08-2029-4e95-9775-16d872e20bdc" />



 # **Microsoft Defender for Cloud Apps Integration**
  - In the Microsoft Defender portal, navigate to:

   Settings -> Endpoints

  - Microsoft Defender for Cloud Apps (MDCA)

Direct link: https://security.microsoft.com/securitysettings/endpoints/integration?tid

  <img width="1467" height="1081" alt="image" src="https://github.com/user-attachments/assets/018f04ec-5ab3-4577-9f39-41f53b1fca68" />

And Settings -> Cloud Apps --> Microsoft Defender for Endpoint

Direct link: https://security.microsoft.com/cloudapps/settings?tabid=app-control&tid

<img width="1415" height="822" alt="image" src="https://github.com/user-attachments/assets/d87e30ea-ced1-46e5-a815-ff1cb81ea8e0" />


# For Defender for Business customers only- Custom Indicators and Web Content filtering **Endpoint Features**
  - In the Microsoft Defender portal, navigate to:

    Settings -> Endpoints

  - Ensure the following features are enabled:
    - Custom Network Indicators
    - Web Content Filtering

Direct link: https://security.microsoft.com/securitysettings/endpoints/integration?tid

  <img width="1467" height="1006" alt="image" src="https://github.com/user-attachments/assets/cd132687-9069-42bc-97ee-285910286be8" />


---

