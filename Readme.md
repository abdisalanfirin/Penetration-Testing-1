## Step 1: Google Dorking

- Using Google, can you identify who the Chief Executive Officer of Altoro Mutual is?
    
    - Karl Fitzgerald

- How can this information be helpful to an attacker?

    - Enabling an attacker to launch an EMAIL whaling phising attack against the CEO of Altoro Mutual

## Step 2: DNS and Domain Discovery

Enter the IP address for demo.testfire.net into Domain Dossier and answer the following questions based on the results:

- Where is the company located?

    - Sunnyvalle, CA

- What is the NetRange IP address?

    - 65.61.137.64 - 65.61.137.127

- What is the company they use to store their infrastructure?

    - Rackspace Backbone Engineering

- What is the IP address of the DNS server?

    - 65.61.137.117

## Step 3: Shodan

- What open ports and running services did Shodan find?

    - Port 80 - Apache tcp, HTTP
    - Port 443 - Apache tcp, HTTPS
    - Port 8080 - Apache tcp, HTTPS

![Open ports](./Images/snap-1.PNG)

## Step 4: Recon-ng

Install the Recon module xssed.
Set the source to demo.testfire.net.
Run the module.

- Is Altoro Mutual vulnerable to XSS?
  
    - YES

![Installing xssed](./Images/snap-2.PNG)

## Step 5: Zenmap

Your client has asked that you help identify any vulnerabilities with their file-sharing server. Using the Metasploitable machine to act as your client's server, complete the following:

- Command for Zenmap to run a service scan against the Metasploitable machine?

    - nmap -T4 -A -v 192.168.0.10 -o metasploitable.nmap
   
![running the nmap script](./Images/snap-5.PNG)

- Bonus command to output results into a new text file named zenmapscan.txt?

    - nmap -sV -oN zenmapscan.txt
   
   ![running the nmap script](./Images/snap-6.PNG)

- Zenmap vulnerability script command?

    - nmap -T4 -A -v --script vulners -p 139,445 192.168.0.10 -o metasploitable.nmap

![Running Nmap and putting in to file](./Images/snap-7.PNG)


- Once you have identified this vulnerability, answer the following questions for your client:

- What is the vulnerability?

    - The 192.168.0.10\tmp fileshare allows for user Anonymous: READ/WRITE access

- Why is it dangerous?

    - This could result in a hacker gaining access to the host server and install malicious code 


- What mitigation strategies can you recommendations for the client to protect their server?

    - Keep Software Up-to-Date.
    - Install Anti-Virus Protection Software.
    - Back Up Critical Data.
    - Invest in Security Training for Employees. 
    - Secure Your Infrastructure. 
    - Implement Multi-Factor Authentication.
    - Identify Threats, Make a Plan, and Learn from Mistakes.

- reference page

    https://www.atlantic.net/hipaa-compliant-hosting/how-to-best-mitigate-cybersecurity-risks-and-protect-your-data/

