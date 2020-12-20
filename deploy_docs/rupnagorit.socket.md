<!-- $ sudo nano /etc/systemd/system/gunicorn.socket -->

[Unit]
Description=rupnagorit socket

[Socket]
ListenStream=/run/rupnagorit.sock

[Install]
WantedBy=sockets.target
