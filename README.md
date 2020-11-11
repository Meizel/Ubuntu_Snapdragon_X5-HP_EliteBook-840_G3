# Ubuntu_Snapdragon_X5-HP_EliteBook-840_G3
add Snapdragon x5 lte modem on debian based linux
# Create systemd service

Create a file /etc/systemd/system/lte.service

Put in the following lines
```service
[Unit]
Description=lte script

[Service]
ExecStart=/lte-check.sh

[Install]
WantedBy=multi-user.target
```

## Shell script

This is the shell script to connect the snapdragon as A modem.

Safe the file in your root directory.

```sh
#!/bin/bash

# Snapdragon X5 startup HP Elitebook 840 G3

sudo usb_modeswitch -v 0x03f0 -p 0x9d1d -u3
```

Make lte-check.sh executable in Terminal 

```sh
sudo chmod -R 755 /lte-check.sh
```

## Enable your lte service

```sh
systemctl enable lte
```

It will run on boot as root.


## Contributing
Pull requests are welcome.
