# Day 08 – Cloud Server Deployment (Nginx)

Today I deployed my first web server on the cloud.
I connected to a cloud VM using SSH, installed Nginx, and made the webpage live.

## Commands Used

- ssh -i JOSH-KEY.pem ubuntu@<PUBLIC-IP>
  Connected to cloud server

- sudo apt update && sudo apt upgrade -y
  Updated server packages

- sudo apt install nginx -y
  Installed Nginx web server

- sudo systemctl start nginx
  Started Nginx service

- sudo systemctl status nginx
  Checked if Nginx is running

- sudo cat /var/log/nginx/access.log
  Viewed Nginx access logs

- sudo cat /var/log/nginx/access.log > nginx-logs.txt
  Saved logs to a file

- scp -i JOSH-KEY.pem ubuntu@<PUBLIC-IP>:~/nginx-logs.txt .
  Downloaded logs to local machine

## Challenges Faced

- At first, the Nginx page was not opening in browser
- I realized port 80 was not allowed in security group
- After allowing HTTP (port 80), the page worked

## What I Learned

- How to connect to a cloud server using SSH
- How to install and manage Nginx
- Importance of security groups and open ports
- Where Nginx logs are stored
- How to copy files from server to local system

## Final Result

- SSH connection successful
- Nginx welcome page accessible from browser
- Logs extracted and downloaded
