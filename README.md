# web-ssl-with-cerbot
# Step 1 — Installing Certbot
```bash
sudo snap install --classic certbot
sudo ln -s /snap/bin/certbot /usr/bin/certbot
```

# Step 2 — Confirming Nginx’s Configuration

```bash 

sudo nano /etc/nginx/sites-available/your_domain

```
- Find the existing server_name line. It should look like the following:/etc/nginx/sites-available/your_domain
```text
...
server_name your_domain www.your_domain;
...

```

# check nginx syntax
```bash 
sudo nginx -t
# reload 

sudo systemctl reload nginx
```

# Step 3 — Allowing HTTPS Through the Firewall

```bash 
sudo ufw status
sudo ufw allow 'Nginx Full'
sudo ufw delete allow 'Nginx HTTP'
sudo ufw status
```
# Step 4 — Obtaining an SSL Certificate
```bash 
sudo certbot --nginx -d your_domain -d your_domain
```

# Step 5 — Verifying Certbot Auto-Renewal
```bash 
sudo certbot renew --dry-run
```


