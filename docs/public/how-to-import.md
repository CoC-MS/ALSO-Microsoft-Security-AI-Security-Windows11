# 📥 How to import

[Public documentation](README.md)

Review [General prerequisites](general-prerequisites.md), [Platform and AI prerequisites](platform-and-ai-prerequisites.md), [Dependencies and import errors](dependencies-and-import-errors.md), and the selected package before starting.

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

## Package-specific import guidance

Select either `ALSO_AI_SECURITY_WINDOWS11_BP` or `ALSO_AI_SECURITY_WINDOWS11_E7`, not the repository root and not both packages. Import or map dependencies before dependent policies, inspect the command-window output, verify every imported object and assignment, and keep Conditional Access policies OFF until a controlled pilot is complete.
