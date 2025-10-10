# SIEM Project

This project covers a two-week study on collecting, processing, and visualizing security events on Elastic SIEM. The work focuses on setting up SNORT IDS, UFW firewall logs, and custom syslog sources, creating parsing rules, and building dashboards in Kibana.  

## 📌 Week 1: Elastic SIEM Setup and Introduction to Log Management

### Tasks Completed
- Installed **Elastic SIEM** on virtual machines.  
- Configured **NGINX Open Source** as a load balancer for Elastic Data nodes.  
- Set up **NGINX Reverse Proxy** for Kibana access.  
- Created the following log sources:
  - **SNORT** (with Talos rules as IDS)  
  - **UFW Firewall** (on Ubuntu)  
  - **Nginx Access Logs** (configured for Elastic deployment)  
  - **Custom Syslog Script** (to generate Linux-based events)  

### Deliverables
1. **Design Artifacts**  
   - Virtual machine architecture (CPU/RAM/disk)  
   - Network design (IP addressing, subnetting, firewall rules)  
   - NGINX load balancer setup draft  
   - Reverse proxy configuration for Kibana (with SSL/TLS)  
   - SNORT + Talos rules configuration plan  
   - Syslog script design and message format  

2. **Elastic SIEM Installation** – Screenshots or video proof  

3. **SNORT + UFW Setup** – Configurations and validation  

4. **Kibana Dashboard** – Initial dashboards for SNORT and UFW logs  

⏱ Completion target: 1 week  

---

## 📌 Week 2: Log Parsing and Dashboard Development

### Tasks Completed
- **Log Parsing Rules** created:
  - **SNORT Parsing** (`/var/log/snort/alert`)
    - Extracted fields: `alert_msg`, `priority`, `gid`, `sid`, `rev`, `src_ip`, `dest_ip`, `proto`, `timestamp`
  - **UFW Parsing** (`/var/log/ufw.log`)
    - Extracted fields: `src_ip`, `dest_ip`, `proto`, `src_port`, `dest_port`, `action`, `length`, `ttl`
  - Tools used: **Grok Patterns**, **Ingest Pipelines (via Kibana > Stack Management)**  

- **Dashboarding**  
  A unified Kibana dashboard was built to visualize both SNORT and UFW events.  

### Visualizations
- 🔹 **Top SNORT Alert Messages** – Pie Chart  
- 🔹 **Source IP Distribution** – Pie Chart  
- 🔹 **Destination IP Distribution** – Pie Chart  
- 🔹 **Protocol Usage Distribution** – Pie Chart  
- 🔹 **Security Events Timeline** – Line Chart  
- 🔹 **UFW Action (ALLOW/DENY)** – Bar Chart  

### Dashboard Summary
| Visualization            | Source | Field        | Description |
|--------------------------|--------|-------------|-------------|
| Top SNORT Alerts         | SNORT  | alert_msg   | Most frequent alerts |
| Source IP Distribution   | UFW    | src_ip      | Frequent source IPs |
| Destination IPs          | Both   | dest_ip     | Targeted hosts |
| Protocol Types           | Both   | proto       | Protocol usage |
| UFW Port Access          | UFW    | dest_port   | Targeted ports |
| UFW Action               | UFW    | action      | ALLOW vs DENY |
| SNORT Timeline           | SNORT  | @timestamp  | Alerts over time |
| UFW Timeline             | UFW    | @timestamp  | UFW events over time |

### Tools and Environment
- **Elastic Stack**: 8.13.4  
- **Elasticsearch**: `192.168.10.11:9200`  
- **Kibana**: `192.168.10.11:5601`  
- **Filebeat**: `ids-snort`, `ufw-logger`  
- **Snort IDS**: 2.9.20  
- **UFW Firewall**: Ubuntu default  
- **Parsing Tools**: Grok Patterns, Ingest Pipelines  
- **Dashboarding**: Kibana Visualizations  

### Conclusion
- Successfully developed parsing rules for SNORT and UFW log sources.  
- Built a customized Kibana dashboard for enhanced security monitoring.  
- Established a scalable and flexible **SIEM framework** as the foundation for future enhancements.  

---

## 📂 Project Structure
- Week-1: Elastic SIEM Installation & Log Sources  
- Week-2: Log Parsing & Dashboard Development  

