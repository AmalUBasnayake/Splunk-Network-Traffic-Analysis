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

![Data Ingestion](Screenshots/w2.png)

### 2. Custom Field Extraction
I used the **Delimiters** method in Splunk to define custom fields such as `src_ip`, `dest_ip`, `protocol`, and `length`, allowing for granular searching.

![Field Extraction](Screenshots/w5.png)

### 3. Data Visualization & Dashboarding
Using SPL queries, I created visualization panels to monitor network behavior.

#### **🔍 Query for Top Source IPs:**
```splunk
index="main" | top limit=10 field3
