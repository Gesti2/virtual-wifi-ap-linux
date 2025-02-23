# virtual-wifi-ap-linux

Installation
```bash
sudo apt-get update
sudo apt-get install dnsmasq hostapd
```

## Configuration

1. Edit the dnsmasq configuration file:
    ```bash
    sudo vim /etc/dnsmasq.conf
    ```
2. Add the following lines to the file:
    ```conf
    # Disable dnsmasq reading any other files like /etc/resolv.conf for nameservers (as preferred)
    no-resolv
    interface=<wifi_interface>
    dhcp-range=<starting_ip>,<ending_ip>,12h
    server=1.1.1.1
    server=8.8.4.4
    ```
3. Save and close the file.
4. Copy the hostapd-example and edit to your preference:
    ```bash
    sudo cp hostapd-example.conf /etc/hostapd/hostapd.conf
    sudo vim /etc/hostapd/hostapd.conf
    ```
5. Save and close the file.

6. Run the initSoftAP script:
    ```bash
    sudo ./initSoftAP <wifi_interface> <internet_interface>
    ```

## Reference Links

- [Using hostapd with dnsmasq to create virtual WiFi access point in Linux](https://nims11.wordpress.com/2013/05/22/using-hostapd-with-dnsmasq-to-create-virtual-wifi-access-point-in-linux/)
- [Internet sharing - ArchWiki](https://wiki.archlinux.org/title/Internet_sharing)