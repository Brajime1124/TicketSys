<header style="background-color: #333; color: white; padding: 20px; text-align: center;">
    <h1>Active Directory Home Lab & osTicket Integration</h1>
    <p style="font-size: 1.2em;">A step-by-step guide to setting up an Active Directory home lab and integrating it with osTicket for IT support ticketing.</p>
</header>

<h2>Prerequisites</h2>
<ul>
    <li>A computer with enough resources (at least 16GB RAM, SSD recommended)</li>
    <li><strong>Virtualization software</strong> (VMware Workstation, VirtualBox, or Hyper-V)</li>
    <li><strong>Windows Server ISO</strong> (2019 or 2022) – available from Microsoft’s evaluation site</li>
    <li><strong>Windows 10/11 ISO</strong> (for client machines)</li>
</ul>

<h2>Step 1: Set Up the Virtualization Environment</h2>
<ol>
    <li>Install your preferred virtualization software.</li>
    <li>Create a new <strong>Virtual Machine (VM)</strong> for Windows Server:
        <ul>
            <li>Allocate at least <strong>4GB RAM, 2 CPU cores</strong></li>
            <li>Set the virtual disk to <strong>50GB</strong> or more</li>
            <li>Mount the <strong>Windows Server ISO</strong> and begin installation</li>
        </ul>
    </li>
    <li>Create additional VMs for Windows 10/11 clients following similar steps.</li>
</ol>

<h2>Step 2: Install Windows Server and Configure Basic Settings</h2>
<ol>
    <li>Boot the server VM and install <strong>Windows Server</strong>.</li>
    <li>Set a <strong>strong administrator password</strong>.</li>
    <li>Assign a <strong>static IP address</strong>:
        <ul>
            <li>Open <strong>Network and Sharing Center</strong> → Change adapter settings.</li>
            <li>Configure the Ethernet adapter with a manual IP (e.g., <code>192.168.1.10</code> for the server).</li>
        </ul>
    </li>
    <li>Rename the server to something meaningful (e.g., <code>DC01</code>).</li>
</ol>

<h2>Step 3: Install Active Directory Domain Services (AD DS)</h2>
<ol>
    <li>Open <strong>Server Manager</strong> and select <strong>Add Roles and Features</strong>.</li>
    <li>Choose <strong>Active Directory Domain Services (AD DS)</strong> and install it.</li>
    <li>After installation, <strong>Promote the server to a domain controller</strong>:
        <ul>
            <li>Select <strong>Add a new forest</strong> (e.g., <code>MyLab.local</code>).</li>
            <li>Set a <strong>Directory Services Restore Mode (DSRM) password</strong>.</li>
            <li>Complete the wizard and restart the server.</li>
        </ul>
    </li>
</ol>

<h2>Step 4: Configure Active Directory and DNS</h2>
<p>Once the server is rebooted:</p>
<ul>
    <li>Open <strong>Active Directory Users and Computers (ADUC)</strong>.</li>
    <li>Create <strong>Organizational Units (OUs)</strong> to structure users and computers.</li>
    <li>Create test <strong>user accounts</strong>.</li>
</ul>

<h1>Integrating osTicket with Active Directory</h1>
<h2>Step 1: Install osTicket</h2>
<ol>
    <li>Download the latest version of <a href="https://osticket.com">osTicket</a>.</li>
    <li>Install a web server stack (Apache/IIS, MySQL, and PHP).</li>
    <li>Extract and place osTicket files in the web root directory.</li>
    <li>Run the osTicket installer via your web browser.</li>
</ol>

<h2>Step 2: Configure MySQL Database</h2>
<ol>
    <li>Create a new MySQL database and user.</li>
    <li>Grant full permissions to the osTicket user.</li>
    <li>Enter database details during installation.</li>
</ol>

<h2>Step 3: Enable Active Directory Authentication</h2>
<ol>
    <li>Go to osTicket Admin Panel → <strong>Manage → Plugins</strong>.</li>
    <li>Enable and configure the LDAP Authentication plugin.</li>
    <li>Enter your domain controller details.</li>
    <li>Test user authentication with an AD account.</li>
</ol>

<h2>Step 4: Configure Ticketing System</h2>
<ol>
    <li>Create help topics and departments.</li>
    <li>Set user roles and permissions.</li>
    <li>Test ticket submission and resolution workflow.</li>
</ol>

<h2>Conclusion</h2>
<p>Integrating osTicket with Active Directory provides a seamless ticketing solution for IT support. With AD authentication, users can log in with their existing credentials, making the system more secure and efficient.</p>

