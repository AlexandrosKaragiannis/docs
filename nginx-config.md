# NGINX Configuration

# Install Nginx
  ```sudo yum install nginx```
# Start Nginx
```sudo systemctl start nginx```
If you are running a firewall, run the following commands to allow HTTP and HTTPS traffic:
```sudo firewall-cmd --permanent --zone=public --add-service=http 
sudo firewall-cmd --permanent --zone=public --add-service=https
sudo firewall-cmd --reload
```
you will probably want to enable Nginx to start when your system boots. To do so, enter the following command:
```sudo systemctl enable nginx```
