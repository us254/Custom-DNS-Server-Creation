

# **Creating a DNS server Guide**

**_Creating a DNS server involves several steps:_**

* Incorporating registration
* Configuring a Linux server
* Setting up Nginx
* Obtaining an SSL certificate with Certbot

Finally, configure your server to manage DNS requests. Below is a simplified guide based on the information you've provided:

**Step 1: Acquire a Server**

Purchase a High-Quality Server: Look for one with a clean setup and low ping to ensure good performance and responsiveness.

**Step 2: Register a Domain**

Register at No-IP: Visit [noip.com](http://noip.com) and create an account.

Set Up Your Domain: Go to the 'My Services' section and navigate to the DNS records section. Here, create a host or subdomain, such as http://gogoli.webhop.me.

**Step 3: Prepare Your Linux Server**

- Open Ports: Ensure ports 80 (HTTP) and 443 (HTTPS) are open on your server firewall.
- Install Nginx:
  ```sh
  sudo apt install nginx
  ```
- Configure Nginx: Edit /etc/nginx/sites-enabled/default to change the server_name to your domain (gogoli.webhop.me in your example).

**Step 4: Obtain an SSL Certificate with Certbot**

- Install Certbot:
  ```sh
  sudo apt install certbot python3-certbot-nginx
  ```
- Run Certbot:
  ```sh
  sudo certbot --nginx -d yourdomain.com
  ```

**Step 5: Configure Nginx and Certbot for Your Domain**

Configure SSL/TLS:

Ensure nginx.conf is properly set with directives managed by Certbot, indicating paths to certificates and keys.

**Step 6: Install Development Tools**

Install Snap and Go:
```sh
sudo snap install go --classic
sudo apt install git
```

**Step 7: Finalize Nginx Configuration**

- Edit nginx.conf: Replace the content with your customized configuration, setting your own domain in place of <YOUR_HOST>.
- Restart Nginx:
  ```sh
  sudo systemctl stop nginx  
  sudo systemctl start nginx
  ```
  
**Step 8: Configure Custom DNS Handling**

- Edit Config.json: Adjust the parameters to match your domain and IP address.
- Deploy Your Service:
  Run the following command : 
  ```sh
  go run main.go
  ```
  
or `go build main.go` for compiling the application.

Background Execution: Use tmux or a similar tool to run your application in the background.

**Conclusion**

Following these steps will help you set up a DNS server capable of redirecting and managing web traffic as per your custom configurations. Remember, managing a DNS server requires ongoing maintenance and security practices to protect against vulnerabilities and ensure your server remains reliable for users.


https://twitter.com/uo0sef/status/1726668570447532352

**Note**

This guide is a simplified summary. Depending on your specific requirements and configurations, additional steps or modifications might be necessary. Always refer to the official documentation for the services and software you are using for the most accurate and secure setup procedures.
```
