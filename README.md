# 🛡️ Network Traffic Analysis Dashboard using Splunk

## 📌 Project Overview
This project demonstrates how to transform raw network packet data (PCAP) into actionable security intelligence. I captured live network traffic from a local environment and used **Splunk Enterprise** to build a comprehensive **Security Operations Center (SOC) Dashboard** for monitoring and threat hunting.

> [!IMPORTANT]
> **Note:** The raw dataset (CSV) is not included in this repository to comply with data privacy and security policies.

---

## 🛠️ Tools & Technologies
* **Wireshark:** Captured network packets and exported metadata to CSV format.
* **Splunk Enterprise:** Used for data ingestion, custom field extraction, and visualization.
* **Search Processing Language (SPL):** Used to query and filter specific security events.

---

## 🚀 Step-by-Step Implementation

### 1. Data Ingestion
The process started by exporting the PCAP file as a CSV from Wireshark. This CSV was then uploaded to the Splunk environment.

![Data Ingestion](Splunk%20Image/w2.png)

### 2. Custom Field Extraction
I used the **Delimiters** method in Splunk to define custom fields such as `src_ip`, `dest_ip`, `protocol`, and `length`, allowing for granular searching.

![Field Extraction](Splunk%20Image/w3.png)

### 3. Data Visualization & Dashboarding
Using SPL queries, I created visualization panels to monitor network behavior.

#### **🔍 Query for Top Source IPs:**

![Field Extraction](Splunk%20Image/w6.png)

![Field Extraction](Splunk%20Image/w9.png)

```splunk
index="main" | top limit=10 field3



📊 Query for Protocol Distribution:
Code snippet
index="main" | stats count by field5
🖼️ Final SOC Dashboard
The final dashboard provides a real-time overview of the network traffic, helping to identify "Top Talkers" and protocol anomalies. The Dark Mode interface ensures high visibility for SOC analysts.

💡 Key Insights & Analysis
🚀 High Traffic Volume: Identified 192.168.10.52 as the primary source of traffic within the network.

🌐 Protocol Distribution: Significant usage of TLSv1.3 and TCP, indicating heavy encrypted web-based activity.

🛡️ Network Hygiene: Monitoring of ARP and DNS queries to ensure they match expected baseline network behavior.
