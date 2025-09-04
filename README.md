# On-Premises Active Directory Deployed in the Cloud (Azure)

<p align="center">
  <img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo" width="200"/>
</p>

##  Overview  
This project demonstrates how to deploy and configure an **on-premises Active Directory environment** inside **Microsoft Azure Virtual Machines**.  

By following this guide, you’ll learn how to:  
- Build and configure a **Virtual Network** in Azure.  
- Deploy **Windows Server 2022** as a Domain Controller (DC-1).  
- Join a **Windows 10 client machine** (Client-1) to the Active Directory domain.  
- Automate user creation with **PowerShell**.  
- Manage accounts with **Group Policy** and security configurations.  

---

## Video Demonstration  
▶️ [YouTube: How to Deploy On-Premises Active Directory in Azure](https://www.youtube.com)  

---

##  Technologies & Tools Used  
- **Microsoft Azure** (Virtual Machines, Networking)  
- **Active Directory Domain Services (AD DS)**  
- **Group Policy Management**  
- **PowerShell**  
- **Remote Desktop Protocol (RDP)**  

---

##  Operating Systems  
- **Windows Server 2022**  
- **Windows 10 (21H2)**  

---

##  High-Level Steps  
1. Prepare Active Directory infrastructure in Azure.  
2. Deploy and configure Active Directory Domain Services.  
3. Create and test domain users (PowerShell automation).  
4. Configure and apply Group Policies.  

---

## 🔧 Deployment & Configuration  

### Step 1: Preparing Active Directory Infrastructure in Azure  
- Create a **Virtual Network**.  
- Deploy **2 Virtual Machines**:  
  - **DC-1 (Domain Controller)**  
  - **Client-1 (Windows 10 client)**  
- Assign a **static private IP** to DC-1.  
- Disable Windows Firewall on DC-1 for connectivity testing.  
- Configure **DNS settings** on Client-1 to use DC-1’s private IP.  
- Verify connectivity with `ping` and `ipconfig`.  

<details>
<summary>📸 Click to view Step 1 screenshots</summary>

<img width="1600" src="https://github.com/user-attachments/assets/d55772b5-487e-4cb0-acfe-c1ade1fe2298" />  

---

<img width="1600" src="https://github.com/user-attachments/assets/3dfa1612-4449-4f86-95ba-87b924cb2b47" />  

---

<img width="1600" src="https://github.com/user-attachments/assets/bd6f8a1c-9a38-48cd-8086-4e52bd1a7631" />  

---

<img width="1600" src="https://github.com/user-attachments/assets/24fa2734-a2e1-416f-8314-adfe52de0e5f" />  

---

<img width="1600" src="https://github.com/user-attachments/assets/060bacae-a942-4499-83eb-b498f42e66ca" />  

---

<img width="1600" src="https://github.com/user-attachments/assets/a6517164-d384-4a6d-882f-44ca272329b3" />  

---

<img width="1600" src="https://github.com/user-attachments/assets/23c9d5cd-1b7d-424b-9cdb-6765eaf298a1" />  

---

<img width="1600" src="https://github.com/user-attachments/assets/2019735b-1b48-42f4-a2b5-ec3e77d792c8" />  

</details>  

---

### Step 2: Deploying Active Directory  
- Install **Active Directory Domain Services** on DC-1.  
- Promote DC-1 as a **Domain Controller**.  
- Create a **new forest**: `mydomain.com`.  
- Add a new **admin user (Jane Doe)**.  
- Join Client-1 to the new domain.  

<details>
<summary>📸 Click to view Step 2 screenshots</summary>

<img width="1600" src="https://github.com/user-attachments/assets/5ee9be30-733d-48ec-9f06-9015fffe9d38" />  

---

<img width="1600" src="https://github.com/user-attachments/assets/6888f45c-29e9-46f3-a149-eced6b29cc5a" />  

---

<img width="1600" src="https://github.com/user-attachments/assets/291f86d2-4081-433e-8f10-b31a1aa74bb6" />  

---

<img width="1600" src="https://github.com/user-attachments/assets/894bf2c8-733d-40c4-ad89-e47e59bcc14f" />  

---

<img width="1600" src="https://github.com/user-attachments/assets/dce8cb50-2e26-41e8-b4da-ad472b056b88" />  

---

<img width="1600" src="https://github.com/user-attachments/assets/9524fabb-980c-451d-98b5-54801c363585" />  

---

<img width="1600" src="https://github.com/user-attachments/assets/de0efa17-116a-419b-ba6f-8155c4cb942e" />  

</details>  

---

### Step 3: Creating Users with PowerShell  
- Add domain users to **Remote Desktop Users** group on Client-1.  
- Run a **PowerShell script** on DC-1 to bulk-create new users.  
- Test login with a sample user account (e.g., `nose.wed`).  

<details>
<summary>📸 Click to view Step 3 screenshots</summary>

<img width="1600" src="https://github.com/user-attachments/assets/0a61881b-dd78-47ee-984c-0894681b19fd" />  

---

<img width="1600" src="https://github.com/user-attachments/assets/1b48f07b-c7f2-4eda-8733-28e03a03f716" />  

---

<img width="1600" src="https://github.com/user-attachments/assets/2206ac3d-3da2-4036-95c6-5d0302204d91" />  

---

<img width="1600" src="https://github.com/user-attachments/assets/c804a2f0-d4eb-4771-9557-6356f768134e" />  

</details>  

---

### Step 4: Group Policy & Account Management  
- Configure **Account Lockout Policy** using Group Policy Management (`gpmc.msc`).  
- Trigger and resolve a **user lockout**.  
- **Enable/disable** user accounts in Active Directory.  
- Audit **security logs** in Event Viewer for lockout activity.  

<details>
<summary>📸 Click to view Step 4 screenshots</summary>

<img width="1600" src="https://github.com/user-attachments/assets/34af0a1c-964d-4cb8-be65-8f18c8579f6c" /> 

---

<img width="1600" src="https://github.com/user-attachments/assets/050df9ef-987e-4a4a-aea2-6abe38043649" />  

---

<img width="1600" src="https://github.com/user-attachments/assets/4f8ac407-d5af-4910-80ca-00641995f28b" />  

---

<img width="1600" src="https://github.com/user-attachments/assets/192b9e7e-186c-441a-9ab0-10afb3e024c7" />  

---

<img width="1600" src="https://github.com/user-attachments/assets/368a787c-9b71-4c5d-a7d6-ef5a50b5bbb2" />  

---

<img width="1600" src="https://github.com/user-attachments/assets/4f1294b2-7252-4086-b64f-b825d06796d8" />  

</details>  

---

##  Learning Outcomes  
Through this project, I gained hands-on experience with:  
- Designing and deploying an Active Directory lab in **Azure**.  
- Configuring **networking, DNS, and IP settings** for domain environments.  
- Automating account creation with **PowerShell scripting**.  
- Applying **Group Policies** for security and account management.  
- Troubleshooting and auditing **Active Directory logs**.  

---

