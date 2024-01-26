# nginx-website

# My Test Website Deployment Guide

This guide provides instructions on deploying the Awesome Website using Nginx.

## Technologies Used

- HTML5
- Nginx

## Prerequisites

- Nginx installed on my Ubuntu server
- Basic understanding of Nginx configuration

## Steps to Deploy

### 1. Clone the Repository

Cloned My Test Website repository to my server:

```bash
https://github.com/DimaBlokhin/nginx-website.git
```
### 2. Nginx Configuration
Created an Nginx server block configuration file for my test website. Path is: "/etc/nginx/sites-available/my-website"

```bash
server {
    listen 80;
    server_name my-website111.com www.my-website111.com;

    root var/www/my-website;
    index index.html;

    location / {
        try_files $uri $uri/ =404;
    }
}
```

Created a symbolic link to enable the server block:
```bash
sudo ln -s /etc/nginx/sites-available/my-website /etc/nginx/sites-enabled/
```
Tested the Nginx configuration for syntax:
```bash
sudo nginx -t
```

Reloaded Nginx to apply changes:
```bash
sudo systemctl restart nginx
```

### 3. Access Your Website
Visited my test website in a web browser: "my-website111.com" and it looks like: 

![Alt текст](https://ibb.co/rfGswYm)

