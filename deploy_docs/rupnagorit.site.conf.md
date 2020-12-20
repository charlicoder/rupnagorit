
<!-- $ sudo nano /etc/nginx/sites-available/rupnagorit -->

server {
    listen 80;
    server_name rupnagorit.com;

    location = /favicon.ico { access_log off; log_not_found off; }
    location /static/ {
        root /home/charlicoder/projects/rupnagorit;
    }

    location / {
        include proxy_params;
        proxy_pass http://unix:/run/rupnagorit.sock;
    }
}
