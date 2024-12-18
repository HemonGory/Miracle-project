# Project Title: Miracle Project Landing Page

## Description
The "Miracle Project Landing Page" is a simple web page hosted on an Nginx server on AWS. This project demonstrates setting up a Linux server, installing Nginx, deploying an HTML page, configuring SSL with Certbot, and making the page accessible securely via HTTPS. The landing page introduces the user and includes basic project information.

## Installation Instructions
Follow the steps below to set up this project on your server:
1. **Provision a Server**: Use AWS EC2 or any other cloud platform to set up a Linux instance (e.g., Ubuntu).
2. **Install Nginx**: On the server, install Nginx using the following command:
   ```bash
   sudo apt update
   sudo apt install nginx
Deploy the HTML Page: Upload the index.html file (with the associated inline CSS) to the server’s web directory (/var/www/html).
Install Certbot for SSL: Install Certbot to set up SSL for the website:
bash
Copy code
sudo apt install certbot python3-certbot-nginx
Configure SSL: Use Certbot to automatically configure SSL for the website:
bash
Copy code
sudo certbot --nginx -d yourdomain.com
(Replace yourdomain.com with your actual domain or IP address.)
Usage Instructions
Once the server is set up:

Open your web browser and navigate to https://yourdomain.com or the public IP address of your server.
The landing page will load, showing the basic information about the project and your bio.
Contributors
Miracle Banor: The creator and main contributor to this project.



License
This project is open source and available under the MIT License. See the LICENSE file for more details.

vbnet
Copy code

### Steps to Add This to Your Project

1. **Create the README File**:
   - Open your terminal and navigate to your project folder.
   - Run `touch README.md` to create the README file.

2. **Edit the README File**:
   - Open the file in VS Code or a text editor of your choice.
   - Copy and paste the content above, replacing placeholders like `yourdomain.com` with your actual domain or project-specific details.

3. **Add the README to Git**:
   - Once you've saved the file, stage it for commit:
     ```bash
     git add README.md
     ```
   - Commit the changes:
     ```bash
     git commit -m "Added README file with project details"
     ```
   - Push to GitHub:
     ```bash
     git push
     ```

Once this is done, your GitHub repository will contain a well-documented README file that explains your project to others. Let me know if you need further assistance! 😊




DOC.TXT
DOCUMENTATION OF WHOLE PROCESS

Launch an AWS EC2 Instance:

Logged into your AWS account.
Created an EC2 instance using the Ubuntu 20.04 AMI.
Selected an instance type (e.g., t2.micro).
Configured the security group to allow the following:
HTTP (port 80): For web traffic.
HTTPS (port 443): For secure web traffic.
SSH (port 22): For remote access to the server.
Access the Instance:

Used SSH to connect to your EC2 instance:
bash
Copy code
ssh -i your-key.pem ubuntu@<instance-public-ip>
Step 2: Installing and Configuring Nginx
Update System Packages:

Ran the following commands to ensure the system is up to date:
bash
Copy code
sudo apt update
sudo apt upgrade -y
Install Nginx:

Installed the Nginx web server:
bash
Copy code
sudo apt install nginx -y
Start and Enable Nginx:

Ensured Nginx is running and set to start on boot:
bash
Copy code
sudo systemctl start nginx
sudo systemctl enable nginx
Verify Nginx Installation:

Opened the browser and accessed the server's public IP (http://<public-ip>) to confirm the default Nginx page.


Step 3: Deploying the HTML Page
At this stage i sued vs code to make the index.html then copy pasted it on the nginx html

Navigate to the Web Root Directory:

Changed to the default web root directory for Nginx:
bash
Copy code
cd /var/www/html
Backup the Default Nginx Page:

Backed up the default page:
bash
Copy code
sudo mv index.nginx-debian.html index.html.bak
Create Your HTML Page:

Created a new index.html file:
bash
Copy code
Restart Nginx to Apply Changes:

Restarted Nginx to serve the new page:
bash
Copy code
sudo systemctl restart nginx
Test the Page:

Opened http://13.60.30.214 in a browser to verify the page.





Step 4: Configuring HTTPS with SSL
Install Certbot:

Installed Certbot and the Nginx plugin:
bash
Copy code
sudo apt install certbot python3-certbot-nginx -y
Obtain and Configure SSL Certificate:

Ran the Certbot command to issue an SSL certificate for your domain:
bash
Copy code
sudo certbot --nginx -d ifyproject.online
Followed the prompts to:
Enter your email address.
Agree to the Terms of Service.
Decline sharing your email address with EFF (optional).
Automatic HTTPS Configuration:

Certbot automatically configured Nginx to redirect HTTP to HTTPS.
Verify HTTPS:

Opened https://ifyproject.online in a browser to confirm the secure connection.




Step 5: Testing and Validation
Verify Domain Accessibility:

Accessed http://ifyproject.online to confirm it redirected to https://ifyproject.online.
Test SSL Auto-Renewal:

Ran the following command to test SSL renewal:
bash
Copy code
sudo certbot renew --dry-run
Verified that the renewal process works without errors.

Public URL:

My website is live at: https://ifyproject.online with SSL.




