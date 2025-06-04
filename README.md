# EC2-Windows-Instance
The objective of this lab was to provision a Windows EC2 instance within the AWS cloud environment, facilitating practical experience with Windows-related services. An existing AWS account was a prerequisite for accessing various environments, and the lab ultimately enhanced familiarity with cloud operations.

This document outlines the steps taken to manually provision a Windows Server 2022 EC2 instance in the AWS console and configure its security group for Remote Desktop Protocol (RDP) access.

Below is a link to my Loom video demonstrating this lab.
https://www.loom.com/share/08ad6689a7144344b30228de78175a75?sid=b9fbc01b-9fe5-4a56-8722-ec2b9020dbbb

## Steps:

1.  **Navigate to the EC2 Dashboard:**
    * Log in to the AWS Management Console.
    * In the services search bar, type "EC2" and select it from the results to go to the EC2 Dashboard.

2.  **Launch a New EC2 Instance:**
    * From the EC2 Dashboard, click on "Instances" in the left-hand navigation pane.
    * Click the "Launch instances" button.

3.  **Choose an Amazon Machine Image (AMI):**
    * **Name:** Provide a descriptive name for your instance (e.g., `Windows-2022-Lab-Instance`).
    * **Application and OS Images (Amazon Machine Image):**
        * In the "Quick Start" tab, search for "Windows".
        * Select an AMI for "Microsoft Windows Server 2022 Base" (or your specific preferred Windows Server 2022 edition). Ensure it's marked as "Free tier eligible" if you want to stay within the free usage limits.

4.  **Choose an Instance Type:**
    * Select an instance type based on your needs (e.g., `t2.micro` or `t3.micro` which are often Free Tier eligible). This determines the CPU, memory, storage, and networking capacity of your instance.

5.  **Configure Key Pair:**
    * **Key pair (login):**
        * If you have an existing key pair you want to use, select it from the dropdown.
        * If not, click "Create new key pair".
            * Enter a key pair name (e.g., `my-windows-keypair`).
            * Choose the key pair type (RSA is common) and private key file format (`.pem` for OpenSSH or `.ppk` for PuTTY if you plan to use PuTTYGen to convert it).
            * Click "Create key pair". Your browser will download the private key file. **Store this file securely, as it's required to decrypt the Windows administrator password and connect to your instance.**

6.  **Review and Launch Instance:**
    * Review all the configured settings in the "Summary" panel on the right.
    * Once satisfied, click the "Launch instance" button.

7.  **Instance Launch Status:**
    * You will be redirected to a page indicating the launch status. Click on the instance ID to go to the "Instances" page where you can monitor its state.
    * Wait for the "Instance state" to change from "Pending" to "Running" and for "Status checks" to pass (e.g., "2/2 checks passed").

8. **Connect to Your Windows Instance:**
    * Select your newly launched instance from the "Instances" list.
    * Click the "Connect" button.
    * Go to the "RDP client" tab.

 * **Download remote desktop file:**
        * Click "Download remote desktop file". This will download an `.rdp` file pre-configured with the instance's public DNS or IP address.
 * **Get Password:**
        * You will need the private key file (`.pem`) you created or selected in Step 5.
        * Click "Get password".
        * Click "Upload private key file" and select your `.pem` file, or paste the contents of the `.pem` file into the text box.
        * Click "Decrypt Password". The Administrator password for your instance will be displayed. **Copy this password and store it securely.**
   * Enter password to connect the Remote Desktop.
