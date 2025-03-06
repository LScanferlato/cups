# cups
cups-docker

podman run -d -p 631:631 --device /dev/bus/usb --name cups anujdatar/cups

Customizing your container

podman run -d --name cups \
    --restart unless-stopped \
    -p 631:631 \
    --device /dev/bus/usb \
    -e CUPSADMIN=admin \
    -e CUPSPASSWORD=password \
    -e TZ="Europe/Rome" \
    -v <persistent-config-folder>:/etc/cups \
    lscanferlato/cups
