# README: Packet Sniffer and Network Analysis Assignment

## **1. Project Overview**
This project involves implementing a raw packet sniffer and analyzing network traffic using a previously captured PCAP file. The assignment is divided into three parts:

1. **Packet Analysis and Metrics Computation** (Extracting key network metrics)
2. **Extended Sniffing for Specific Queries** (PCAP-specific questions)
3. **Live Packet Capture and Website Analysis** (Capturing network packets and analyzing website requests)

---

## **2. Requirements**
### **Software and Tools Needed:**
- **Python 3.x**
- **Scapy** (for packet analysis)
- **Wireshark** (for live packet capture)
- **Tcpreplay** (for packet replay)
- **Matplotlib** (for plotting graphs)
- **Pandas** (for data processing)
- **Curl / Developer Tools** (for HTTP request analysis)
- **GitHub** (for code submission)

### **Installation Steps:**
Run the following command to install required Python libraries:
```sh
pip install scapy matplotlib pandas
```
For Linux/macOS, install **Tcpreplay** using:
```sh
sudo apt-get install tcpreplay  # Debian/Ubuntu
brew install tcpreplay  # macOS
```
For Wireshark installation, download it from [https://www.wireshark.org/download.html](https://www.wireshark.org/download.html)

---

## **3. Instructions to Execute and Reproduce Results**
### **Part 1: Packet Sniffer Development and Analysis**
#### **Step 1: Select the Correct PCAP File**
1. Find your **Team ID** from the provided Google Sheet.
2. Compute **X = (Team ID) % 9** to select the correct PCAP file.
3. Download the file from the provided repository.

#### **Step 2: Run Packet Sniffer**
Run the packet sniffer script to analyze the PCAP file:
```sh
python packet_sniffer.py X.pcap
```
##### **Metrics Computed:**
- Total data transferred (bytes) and number of packets
- Minimum, maximum, and average packet sizes (Histogram plot)
- Unique **Source-Destination Pairs** (IP:Port)
- Dictionary of flows per IP address
- Top speed in `pps` and `mbps`

#### **Step 3: Visualize Results**
To generate plots:
```sh
python generate_plots.py
```
This will output histograms and other visualizations for analysis.

#### **Step 4: Packet Replay (Optional)**
To replay packets using **tcpreplay**:
```sh
tcpreplay --intf1=eth0 --mbps=10 X.pcap
```
Run your sniffer program concurrently to capture and verify the replayed traffic.

---

### **Part 2: PCAP-Specific Questions**
Run the extended sniffer with:
```sh
python extended_sniffer.py X.pcap
```
This script processes the PCAP file to answer the specific questions outlined in the assignment.

---

### **Part 3: Live Packet Capture and Website Analysis**
#### **Step 1: Capture Network Packets using Wireshark**
1. Open **Wireshark**.
2. Select your active network interface (Wi-Fi/Ethernet).
3. Click **Start Capture** and perform regular web activities.
4. Save the captured traffic as `Q3.pcap`.

#### **Step 2: Identify Application Layer Protocols**
Use the Wireshark **Statistics** tab to identify at least 5 lesser-known application layer protocols.

#### **Step 3: Analyze Website Requests**
For each website (**canarabank.in**, **github.com**, **netflix.com**):
1. Open **Developer Tools** (`Ctrl + Shift + I` on Chrome/Edge, `F12` on Firefox).
2. Go to **Network Tab**, reload the page (`F5`).
3. Identify the **Request Line**:
   - Method, URL, and HTTP Version.
4. Check if the **Connection is Persistent**:
   - Look for the `Connection: keep-alive` header.
5. Extract 3 header field names and values from request/response.
6. Identify any **HTTP error codes** encountered and describe them.

#### **Step 4: Capture Performance Metrics and Cookies**
1. In Developer Tools, go to the **Performance Tab**.
2. Click **Start Profiling and Reload Page**.
3. Capture a screenshot and note performance metrics (Load Time, DOM Content Load, etc.).
4. Check **Cookies** in the **Application Tab**.
   - Report cookie names, values, and associated flags from request and response headers.
   


---

## **5. Contact and Support**
For any queries, reach out to your instructor or discuss with your teammate. Happy coding! 🚀

