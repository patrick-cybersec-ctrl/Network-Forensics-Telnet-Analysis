# Project 1: Telnet Network Forensic Analysis

## Executive Summary
This project demonstrates the security risks of using unencrypted protocols. By capturing and analyzing Telnet (Port 23) traffic, I successfully extracted user credentials and identified network anomalies.

## Tools Used
* **Wireshark:** Packet capture and protocol analysis.
* **TCP Stream Reconstruction:** To view the application-layer dialogue.

## Technical Deep-Dive

### 1. Traffic Identification
I isolated Telnet traffic to observe the handshake between the client (`192.168.0.2`) and the server (`192.168.0.1`).

### 2. Credential Extraction
Using the **Follow TCP Stream** method, I reconstructed the session to reveal the plaintext login:
* **Username:** fake
* **Password:** user

### 3. Data Integrity & Hex Analysis
I verified the raw data by correlating the ASCII character **'U'** to its Hexadecimal value **'55'**, proving a deep understanding of packet-level data representation.

### 4. Anomaly Detection
The capture revealed **Malformed Packets**, indicating potential protocol instability or a service-level error during the session.

## Mitigation Recommendations
* **Disable Telnet:** Transition all remote management to **SSH (Port 22)**.
* **Encryption:** Implement TLS/SSL for all data in transit to prevent credential harvesting.
