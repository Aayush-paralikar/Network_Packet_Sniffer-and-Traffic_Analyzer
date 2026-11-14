# Network Packet Sniffer & Traffic Analyzer

A Python-based network packet capture and traffic analysis tool built with **Scapy**. The application captures live network packets, identifies common protocols, extracts IP addresses and transport-layer information, maintains real-time traffic statistics, and exports captured packets for further analysis using tools such as Wireshark.

---

## 📌 Project Overview

The **Network Packet Sniffer & Traffic Analyzer** is designed to provide visibility into network traffic at the packet level.

The tool captures packets from a selected network interface and analyzes traffic across protocols such as:

- TCP
- UDP
- ICMP
- ARP
- Other IP traffic

For each captured packet, the analyzer can extract information such as:

- Source IP address
- Destination IP address
- Source port
- Destination port
- Protocol
- Packet size
- Packet count

The application also maintains traffic statistics and can save captured packets in **PCAP format** for offline inspection and troubleshooting using Wireshark.

---

## 🎯 Objectives

The main objectives of this project are to:

- Understand packet-level network communication.
- Monitor live network traffic.
- Analyze TCP/IP traffic and common network protocols.
- Extract useful packet metadata.
- Generate protocol-wise traffic statistics.
- Identify frequently communicating hosts and ports.
- Support network troubleshooting through packet capture.
- Export packet captures for detailed offline analysis.

---

## 🚀 Features

### 1. Real-Time Packet Capture

Captures live network packets using Scapy and processes them as they arrive.

### 2. Protocol Identification

Identifies and categorizes common traffic types including:

- TCP
- UDP
- ICMP
- ARP
- IP
- Other/non-IP traffic

### 3. Packet-Level Information

For IP-based traffic, the application extracts:

- Source IP
- Destination IP
- Protocol

For TCP/UDP traffic, it additionally extracts:

- Source port
- Destination port

### 4. Traffic Statistics

The analyzer maintains statistics including:

- Total packets captured
- Total traffic volume
- Average packet size
- Protocol distribution
- Top source IP addresses
- Top destination IP addresses
- Frequently observed destination ports

### 5. Live Statistics

Traffic statistics can be displayed during packet capture to provide real-time visibility into network activity.

### 6. PCAP Export

Captured packets can be saved in `.pcap` format for later analysis.

PCAP files can be opened using:

**Wireshark**

This allows deeper investigation of:

- TCP handshakes
- DNS traffic
- HTTP/HTTPS communication
- ICMP traffic
- Packet timing
- Protocol headers
- Network conversations

### 7. Configurable Capture

The application supports configurable:

- Capture duration
- Protocol filtering
- PCAP export

---

## 🏗️ System Architecture

```text
                    ┌──────────────────────┐
                    │   Network Interface  │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │   Scapy Packet       │
                    │      Capture         │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │   Packet Handler &    │
                    │   Protocol Detection  │
                    └──────────┬───────────┘
                               │
              ┌────────────────┼────────────────┐
              ▼                ▼                ▼
        ┌──────────┐     ┌────────────┐   ┌──────────────┐
        │ TCP/UDP  │     │ ICMP / ARP │   │ Other Traffic│
        │ Analysis │     │   Analysis │   │   Analysis   │
        └────┬─────┘     └──────┬─────┘   └──────┬───────┘
             │                  │                │
             └──────────────────┼────────────────┘
                                ▼
                    ┌──────────────────────┐
                    │ Traffic Statistics & │
                    │      Analysis        │
                    └──────────┬───────────┘
                               │
                ┌──────────────┴──────────────┐
                ▼                             ▼
       ┌────────────────┐             ┌────────────────┐
       │ Console Output │             │  PCAP Export   │
       └────────────────┘             └───────┬────────┘
                                              │
                                              ▼
                                       ┌─────────────┐
                                       │  Wireshark  │
                                       └─────────────┘
```

---

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| **Python** | Core application development |
| **Scapy** | Packet capture and packet
