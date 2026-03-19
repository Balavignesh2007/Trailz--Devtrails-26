Trailz--Devtrails-26
Git hub repository from Team mebers :- P.Harsha datta,A.Naga koushtub,B.Balavignesh, Ananya Kavuri, K. Sahithi Reddy
#  AI-Powered Insurance Claim Verification System  
### DEVTrails 2026 — Phase 1 Submission  

**Parametric Insurance • Fraud Detection • Anti-Spoofing • Blockchain Settlement**

---

##  Problem Statement
We propose a fully automated, AI-driven parametric insurance platform for gig-economy delivery partners.  

The system verifies claims triggered by real-world events (extreme weather, floods, curfews) using:
- Multi-source ground-truth data  
- Machine learning fraud detection  
- Transparent blockchain settlement  

It is specifically designed to resist advanced adversarial attacks, including coordinated GPS spoofing syndicates.  

---

##  Proposed Solution  

Delivery partners submit claims via a mobile application including:
- Location  
- Date & time  
- Incident type (rain, flood, curfew)  
- Supporting information  

###  Workflow  
1. Claim submission → Unique tracking ID generated  
2. AI Agent collects weather & government data  
3. ML models detect fraud and validate claims  
4. Decision Engine approves, flags, or rejects  

---

##  Technical Stack  

### AI Agent Layer  
LangChain, AutoGen, GPT-4 / Claude, OpenWeather API, Government APIs  

### Machine Learning Layer  
XGBoost, Isolation Forest, BERT, Graph Neural Networks, MLflow  

### Blockchain Layer  
Ethereum / Polygon, Solidity, Chainlink, IPFS  

### Backend Layer  
FastAPI, Kafka, Celery + Redis, JWT, NGINX  

### Database Layer  
PostgreSQL, MongoDB, Pinecone / FAISS, InfluxDB  

### Frontend Layer  
React Native, Next.js, Socket.io, Tailwind CSS  

### Infrastructure  
Docker, Kubernetes, Vercel, Render, Prometheus, Grafana, ELK, GitHub Actions  

# Adversarial Defense & Anti-Spoofing Strategy

##  Problem Statement
This system is designed to detect and prevent fraudulent insurance claims made using GPS spoofing and coordinated syndicate attacks.

**Core Principle:**  
GPS is treated as a weak, forgeable signal.  
The system relies on multi-layer corroboration using independent and hard-to-fake signals.

---

##  1. Genuine Partner vs GPS Spoofer

###  Key Insight
The system does not trust GPS alone — it corroborates it with multiple signals.

---

###  1.1 Multi-Layer Location Corroboration

Each claim must pass the following verification layers:

- **Wi-Fi & Cell Tower Triangulation**
  - Captures nearby SSIDs & tower IDs
  - Detects mismatch between claimed and actual environment

- **IP Geolocation Cross-Check**
  - Compares public IP location with GPS
  - Flags VPN/proxy usage

- **Barometric Pressure Sensor**
  - Verifies outdoor weather consistency
  - Detects indoor vs outdoor conditions

- **Motion Sensors (Accelerometer & Gyroscope)**
  - Identifies real-world movement patterns
  - Detects stationary spoofing behavior

- **Camera-Based Verification (Optional)**
  - Short ambient video validation
  - Detects rain, flood, low visibility (no biometric storage)

---

###  1.2 Behavioural Baseline Comparison

Each partner has a historical movement profile:
- Typical routes
- Average speeds
- Working hours
- Dwell locations

**Fraud Signal:**  
Sudden teleportation → highly suspicious

---

###  1.3 Environmental Ground-Truth Validation

Before device data is considered:

- Weather APIs (OpenWeather, satellite data)
- Government curfew/restriction APIs

**Auto-Reject Rule:**  
Claims are rejected if no real-world event exists.

---

##  2. Data Signals & Spoofing Resistance

| Category | Data Points | Resistance |
|----------|------------|------------|
| GPS | Coordinates, altitude, accuracy | LOW |
| Network | Wi-Fi, BSSID, cell towers, IP | HIGH |
| Sensors | Barometer, accelerometer, gyro | HIGH |
| Temporal | Timing vs shift schedule | MEDIUM |
| Behaviour | Historical patterns | HIGH |
| External APIs | Weather, curfew, flood data | VERY HIGH |
| Social Graph | Group patterns, timestamps | VERY HIGH |
| NLP | Claim text analysis | MEDIUM |

---

##  3. Coordinated Ring Detection

###  Graph-Based Fraud Detection

- **Nodes** → Delivery partners  
- **Edges** → Shared patterns:
  - Same timestamps
  - Same locations
  - Same network signals
  - Social links

**Alert Trigger:**
- ≥10 accounts
- ≥85% correlated timing

➡️ Automatic payout freeze + investigation

---

##  4. UX Design: Protecting Honest Workers

###  4.1 Trust Tier Model

| Tier | Profile | Verification Needed | Fraud Threshold |
|------|--------|--------------------|----------------|
| Tier 1 | Trusted (12+ months) | 2 signals | 5+ flags |
| Tier 2 | Standard | 3 signals | 3+ flags |
| Tier 3 | New/Flagged | 4+ signals | 1+ flag |

---

###  4.2 Graduated Response Workflow

1. **Auto-Approve**
   - No anomalies → instant payout

2. **Soft Flag**
   - Minor mismatch
   - Request additional proof
   - Hold ≤ 4 hours

3. **Manual Review**
   - Multiple anomalies
   - Human + AI explainability report
   - SLA: 24 hours

4. **Auto-Reject**
   - Strong fraud signals
   - Appeal always allowed

---

### 4.3 Network Drop Tolerance

Designed for real-world conditions:

- 90-min delayed submission allowed
- Sparse sensor data NOT penalized
- Falls back to environmental APIs
- Full audit trail for appeals

---

## Design Principle: Explainability

- No black-box decisions  
- Every output includes:
  - Signal breakdown
  - Reason for decision  

**Human review always available**  
**Appeals guaranteed**

---

##  System Architecture

```plaintext
CLAIM SUBMISSION (Mobile App)
        ↓
ANTI-SPOOFING SIGNAL LAYER
GPS | Wi-Fi/Cell | Sensors | IP | Behavior
        ↓
AI AGENT — GROUND TRUTH
Weather APIs | Govt APIs | Satellite Data
        ↓
ML FRAUD ENGINE
XGBoost | Isolation Forest | BERT | GNN
        ↓
DECISION ENGINE
Auto-Approve | Soft Flag | Review | Reject
        ↓
BLOCKCHAIN LAYER
Smart Contract Payout + IPFS Storage
