To scan IP addresses on a network from a Windows machine, you can use a few different tools and methods. Below are a few common methods to achieve this:


### 2. **Using `arp` (Address Resolution Protocol) Table**
After you’ve pinged devices, you can use the `arp` command to get a list of IP addresses and their corresponding MAC addresses that are currently in your local network.

#### Steps:
1. Open **Command Prompt**.

2. Type the following command:

```bash
arp -a
```

This will display the IP addresses and corresponding MAC addresses of devices that your computer has communicated with recently.

---

### 3. **Using `Advanced IP Scanner` (Free Tool)**
For a more detailed and user-friendly approach, you can use a third-party tool like **Advanced IP Scanner**.

#### Steps:
1. Download **[Advanced IP Scanner](https://www.advanced-ip-scanner.com/)** and install it.
   
2. Open the program, and it will automatically scan your local network for connected devices.

3. The scan will show you a list of all devices, including IP addresses, device names, and MAC addresses.

---

### 4. **Using Nmap (Network Mapper)**
Nmap is a very powerful tool for network discovery and scanning. You can install it on Windows and use it to scan an IP range.

#### Steps:
1. Download and install **[Nmap](https://nmap.org/download.html)**.

2. Open **Command Prompt** (or **Nmap's GUI** called Zenmap) and run the following command to scan a range of IPs:

```bash
nmap -sn 192.168.1.0/24
```

**Explanation:**
- `-sn` tells Nmap to perform a "ping scan," which only checks if the device is online without doing a full port scan.
- `192.168.1.0/24` is the network range to scan (you can adjust it according to your network).

---

### 5. **Using PowerShell (for a Scripted Scan)**
You can use PowerShell to scan the IP range and check for live devices on the network.

#### Steps:
1. Open **PowerShell** as an administrator.

2. Run the following script to check a range of IP addresses:

```powershell
1..254 | ForEach-Object { Test-Connection -ComputerName "192.168.1.$_" -Count 1 -Quiet }
```

This will ping all IP addresses in the range `192.168.1.1` to `192.168.1.254`. If a device responds, the result will be `True`.

---

### Conclusion:
- For a quick and simple scan, you can use the **Command Prompt** with `ping` or `arp` commands.
- For more thorough and user-friendly scanning, **Advanced IP Scanner** is a great option.
- If you need more advanced features like OS detection or open port scanning, consider using **Nmap**.

Let me know if you'd like more information on any of these methods!
