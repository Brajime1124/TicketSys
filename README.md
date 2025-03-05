# Active Directory Home Lab & osTicket Integration  
A step-by-step guide to setting up an **Active Directory Home Lab** and integrating it with **osTicket**, a ticketing system commonly used in IT support environments. By the end of this guide, you'll have a functional help desk system where users can submit support requests, and IT staff can manage and resolve issues efficiently.

---

## 🛠 Prerequisites  
Before we begin, ensure you have the following:  

- A computer with at least **16GB RAM** (an SSD is highly recommended for better performance).  
- **Virtualization software** (VMware Workstation, VirtualBox, or Hyper-V).  
- **Windows Server ISO** (2019 or 2022) – available from Microsoft’s evaluation site.  
- **Windows 10/11 ISO** (for client machines).  

---

## 🚀 Step 1: Setting Up the Virtualization Environment  
To start, we'll create virtual machines (VMs) for both **Windows Server** and **Windows Client**.  

1. **Install your preferred virtualization software** (VMware Workstation, VirtualBox, or Hyper-V).  
2. **Create a new Virtual Machine (VM) for Windows Server:**  
   - Allocate **at least 4GB RAM and 2 CPU cores**.  
   - Set the virtual disk size to **50GB or more**.  
   - Mount the **Windows Server ISO** and begin the installation process.  
3. **Create additional VMs for Windows 10/11 clients** following similar steps.  

---

## 🖥 Step 2: Installing Windows Server and Configuring Basic Settings  
Once your **Windows Server VM** is up and running:  

1. Complete the **Windows Server installation** and set a **strong administrator password**.  
2. **Assign a static IP address** to ensure reliable network connectivity:  
   - Open **Network and Sharing Center → Change adapter settings**.  
   - Configure the Ethernet adapter with a manual IP (e.g., `192.168.1.10` for the server).  
3. **Rename the server** to something meaningful, like `DC01` (Domain Controller 01).  

---

## 🔧 Step 3: Installing Active Directory Domain Services (AD DS)  
Now, let’s turn this Windows Server into a **Domain Controller**.  

1. Open **Server Manager** and select **Add Roles and Features**.  
2. Choose **Active Directory Domain Services (AD DS)** and install it.  
3. Once installed, **promote the server to a domain controller**:  
   - Select **Add a new forest** and enter a domain name (e.g., `MyLab.local`).  
   - Set a **Directory Services Restore Mode (DSRM) password** for recovery purposes.  
   - Complete the setup and **restart the server**.  

---

## 🛠 Step 4: Configuring Active Directory and DNS  
After the server reboots:  

1. Open **Active Directory Users and Computers (ADUC)**.  
2. Create **Organizational Units (OUs)** to organize users and computers.  
3. Add **test user accounts** to simulate real users.  

---

# 🎫 Integrating osTicket with Active Directory  
Now that Active Directory is set up, let’s integrate **osTicket** to create a help desk system for IT support.  

## 📥 Step 1: Installing osTicket  
1. Download the latest version of **osTicket** from [osTicket’s official site](https://osticket.com/download).  
2. Install a **web server stack** such as Apache/IIS, MySQL, and PHP.  
3. Extract the osTicket files and place them in your **web root directory**.  
4. Run the **osTicket installer** through your web browser.  

---

## 💾 Step 2: Configuring the MySQL Database  
1. Open MySQL and create a new **database and user** for osTicket.  
2. Grant full permissions to the osTicket user.  
3. Enter the **database details** during the osTicket installation process.  

---

## 🔑 Step 3: Enabling Active Directory Authentication  
1. In the osTicket Admin Panel, navigate to **Manage → Plugins**.  
2. Enable and configure the **LDAP Authentication plugin**.  
3. Enter your **domain controller details** (`DC01` or `MyLab.local`).  
4. Test authentication using an **Active Directory user account**.  

---

## 🎟 Step 4: Configuring the Ticketing System  
1. Create **help topics and departments** to categorize IT support requests.  
2. Set **user roles and permissions** to control access levels.  
3. Test the **ticket submission and resolution workflow** to ensure smooth operation.  

---

## ✅ Conclusion  
By integrating **osTicket** with **Active Directory**, you now have a fully functional **IT help desk system** that allows users to log in with their domain credentials and submit support requests. This setup is similar to what you’d find in a real corporate environment, making it an excellent hands-on project for IT professionals looking to gain real-world experience.  

---

💡 **Next Steps:**  
- Expand your help desk with **custom email notifications**.  
- Implement **group policies** to control user access further.  
- Explore **PowerShell automation** to enhance your Active Directory management.  

---

This guide serves as both a **learning tool** and a **practical project** to showcase my IT skills.🚀  
