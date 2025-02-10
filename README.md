# 🔒 AI-Powered VPN Firewall  
An **AI-driven network security** project that detects **VPN usage** in network traffic and dynamically enforces firewall rules using **nftables**.  

---
## 🚀 Features  
✔ **AI-Powered VPN Detection** – Uses machine learning to analyze network patterns.  
✔ **Real-Time Firewall Enforcement** – Blocks VPN connections dynamically using nftables.  
✔ **Traffic Sniffing** – Captures network packets with tcpdump for AI analysis.  
✔ **Admin Dashboard** – React/Vue-based UI for real-time monitoring & rule management.  
✔ **Secure API** – JWT authentication to restrict access to firewall settings.  
✔ **Scalable & Modular** – Easily extendable with new security modules.  
---
## 📡 How It Works  

### 🔍 **Traffic Capture & Feature Extraction**  
- `traffic_sniffer.py` – Captures network packets for analysis.  
- `feature_extractor.py` – Converts raw data into AI-friendly input.  

### 🧠 **AI-Based VPN Detection**  
- `vpn_detector.py` – Uses a trained AI model to detect VPN usage.  
- If VPN traffic is detected, it triggers `firewall_manager.py` to block the IP.  

### 🔥 **Firewall & Security Management**  
- `firewall_manager.py` – Manages firewall rules dynamically.  
- `vpn_signatures.py` – Maintains a local VPN signature database for faster detection.  
- `logger.py` – Stores AI detections and firewall logs.  

### 📡 **Admin API & Web Dashboard**  
- `api/main.py` – FastAPI backend for UI interaction.  
- `frontend/src` – React/Vue UI for real-time VPN monitoring.  
---
## 📌 Project Structure  
```plaintext
📂 vpn-firewall-ai
├── 📂 backend (AI logic, traffic capture, and firewall)
│   ├── 📂 core (Essential modules)
│   │   ├── traffic_sniffer.py - Traffic capture using tcpdump
│   │   ├── feature_extractor.py - Extracts data for AI analysis
│   │   ├── vpn_detector.py - AI model + nftables integration
│   │   ├── firewall_manager.py - nftables-based firewall
│   │   ├── vpn_signatures.py - VPN signature database
│   │   ├── logger.py - Log handling and storage
│   ├── 📂 api (API for UI and admin control)
│   │   ├── main.py - FastAPI for logs and firewall commands
│   │   ├── routes.py - REST endpoints for UI and firewall control
│   │   ├── security.py - Authentication and user management
│   ├── 📂 database (Logs and AI detections)
│   │   ├── database.py - PostgreSQL connection
│   │   ├── models.py - Database models
│   │   ├── db_migrations/ - Database schema migrations
│   ├── 📂 configs (Configuration files)
│   │   ├── config.yaml - General settings
│   │   ├── firewall_rules.json - Firewall settings
│   │   ├── ai_model.pkl - Trained AI model
│   ├── requirements.txt - Python dependencies
│   ├── run_backend.sh - Script to start the backend
├── 📂 frontend (Monitoring dashboard)
│   ├── 📂 src
│   │   ├── Dashboard.js - UI for administrators
│   │   ├── Settings.js - Firewall rule configuration
│   │   ├── Login.js - Admin authentication system
│   │   ├── Stats.js - Graphs and VPN detection statistics
│   ├── package.json - React/Vue dependencies
│   ├── index.html - Main page
│   ├── run_frontend.sh - Script to start the UI
├── 📂 scripts (Automation and deployment)
│   ├── install_dependencies.sh - Installs all dependencies
│   ├── setup_firewall.sh - Initializes firewall rules
│   ├── train_ai_model.py - AI training script
│   ├── export_logs.py - Exports logs in CSV format
├── 📂 tests (Automated tests for each component)
│   ├── test_sniffer.py - Traffic capture tests
│   ├── test_ai.py - AI model tests
│   ├── test_firewall.py - Firewall tests
├── docker-compose.yml - Docker container configuration
├── README.md - Usage instructions
├── .env - Environment variables for security



