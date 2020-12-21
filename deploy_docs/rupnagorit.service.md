<!-- $ sudo nano /etc/systemd/system/rupnagorit.service -->

[Unit]
Description=rupnagorit daemon
Requires=rupnagorit.socket
After=network.target

[Service]
User=charlicoder
Group=www-data
WorkingDirectory=/home/charlicoder/projects/rupnagorit
ExecStart=/home/charlicoder/projects/rupnagorit/venv/bin/gunicorn \
          --access-logfile - \
          --workers 2 \
          --bind unix:/run/rupnagorit.sock \
          core.wsgi:application

[Install]
WantedBy=multi-user.target
