# Disconnect_a_device_from_wifi

## Using iptables   

### First, you'll need to identify the MAC address of the device you want to disconnect. You can do this using a tool like arp-scan:

```bash
sudo apt-get install arp-scan
sudo arp-scan --localnet
```
Once you have the MAC address, you can block it using iptables:   
```bash
sudo iptables -A INPUT -m mac --mac-source [MAC_ADDRESS] -j DROP
```
#### Replace [MAC_ADDRESS] with the MAC address of the device you want to disconnect.

## If you want to disconnect  
 list the current iptables rules along with their line numbers:  

 ```bash
sudo iptables -L --line-numbers
```

Once you've identified the rule number, you can delete it using the following command:   
```bash
sudo iptables -D INPUT [rule_number]
```

