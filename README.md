# Task 5: Capture and Analyze Network Traffic Using Wireshark

### Objective
Capture live network packets using **Wireshark**, identify common **network protocols**, and understand how data travels between systems.

---

## Tool Used
- **Wireshark** – a free and open-source tool used to capture and analyze network packets in real time.

---

## Steps Performed

### **1. Install Wireshark**
If not already installed:
```bash
sudo apt install wireshark -y
````


**Screenshot 1:** Installation and configuration of Wireshark

<p align="center">
  <img src="https://github.com/Tanya0xCyber/network-traffic-analysis-wireshark/blob/main/screenshots/wireshark-install.png" width="80%">
</p>

---

### **2. Start Packet Capture**

1. Open **Wireshark**.
2. Select your **active network interface** (usually `eth0`, `wlan0`, or similar).
3. Click **Start Capturing** (the blue shark fin icon).

**Screenshot 2:** Wireshark capture started

<p align="center">
  <img src="https://github.com/Tanya0xCyber/network-traffic-analysis-wireshark/blob/main/screenshots/wireshark_interface.png" width="80%">
</p>

---

### **3. Generate Network Traffic**

To see multiple protocols, open a terminal and run these commands (one by one):

#### **a. ICMP (Ping)**

```bash
ping -c 4 google.com
```

➡ Generates ICMP packets (used for checking connectivity).

#### **b. DNS (Domain Name System)**

```bash
nslookup google.com
```

➡ Generates DNS queries that resolve domain names to IP addresses.

#### **c. HTTP and TCP**

```bash
curl http://example.com
```

➡ Generates HTTP requests over TCP connections.

**Screenshot 3:** Commands used to generate traffic

<p align="center">
  <img src="screenshots/traffic-generation.png" width="80%">
</p>

---

### **4. Stop the Capture**

After running the commands for 1–2 minutes, click the **red stop button** in Wireshark.

**Screenshot 4:** Capture stopped

<p align="center">
  <img src="screenshots/stop-capture.png" width="80%">
</p>

---

### **5. Filter Packets by Protocol**

Use filters in Wireshark to view specific protocols:

| Protocol | Filter Keyword | Purpose                     |
| -------- | -------------- | --------------------------- |
| ICMP     | `icmp`         | Ping requests and replies   |
| DNS      | `dns`          | Domain name lookups         |
| TCP      | `tcp`          | Transport layer connections |
| HTTP     | `http`         | Web traffic                 |

**Screenshot 5:** Protocol filters applied in Wireshark

<p align="center">
  <img src="screenshots/protocol-filters.png" width="80%">
</p>

---

### **6. Save the Capture**

Export your capture file as:

```
File → Save As → traffic-analysis.pcap
```

**Screenshot 6:** Exporting `.pcap` file

<p align="center">
  <img src="screenshots/export-pcap.png" width="80%">
</p>

---

## Summary of Findings

| Protocol | Description                                       | Example                                           |
| -------- | ------------------------------------------------- | ------------------------------------------------- |
| **ICMP** | Used by `ping` to check if a host is reachable.   | Echo request/reply between your system and Google |
| **DNS**  | Translates domain names into IP addresses.        | `nslookup google.com`                             |
| **TCP**  | Establishes reliable connections between systems. | Used when accessing websites                      |
| **HTTP** | Application layer protocol for web traffic.       | `curl http://example.com`                         |

**Screenshot 7:** Example captured ICMP packets

<p align="center">
  <img src="screenshots/icmp-example.png" width="80%">
</p>

---

### Outcome:

* Successfully captured live packets for **ICMP**, **DNS**, **TCP**, and **HTTP** protocols.
* Gained practical knowledge of how different types of traffic look in Wireshark.
* Exported `.pcap` file for further analysis.

---

### Deliverables

* `traffic-analysis.pcap` – packet capture file
* `README.md` – task documentation with screenshots and explanation

---
