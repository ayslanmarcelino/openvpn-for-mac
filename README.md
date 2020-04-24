# OpenVpn for MacOS

This is a helper script designed to integrate OpenVPN with the `update-resolv-conf`.


# Installation

First you need the [OpenVpn](https://openvpn.net/vpn-server-resources/connecting-to-access-server-with-macos/) installed in your MacOS.

    brew install openvpn

Then you create a folder in the `/etc` directory

    cd /etc
    mkdir openvpn

Then you download the `update-resolv-conf` file and paste it in the `/etc/openvpn` folder, after that, use the command below to give permission:

    chmod +X update-resolv-conf

Open the `.ovpn` file and and find the following lines and keep as below:

     For no systemd Linux
    up /etc/openvpn/update-resolv-conf
    down /etc/openvpn/update-resolv-conf
    
     For systemd Linux
    #up /etc/openvpn/update-systemd-resolved
    #down /etc/openvpn/update-systemd-resolved

## Run OpenVpn

Run the command:

    export PATH=/usr/local/sbin:$PATH
    sudo openvpn --auth-nocache --config YourDirectory/File.ovpn

## Problems With Connection

If you have problems with the connection, follow:

`Open Network Preferences -> Advanced -> DNS`

In DNS Servers add Google DNS (`8.8.8.8` or `8.8.4.4`), if it's not already there, or other DNS of your choice.

## Authors

- [Ayslan Marcelino](https://github.com/ayslanmarcelino)
- [Anderson Fernandes](https://github.com/andersonfernandes)
