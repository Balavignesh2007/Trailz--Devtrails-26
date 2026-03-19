Trailz--Devtrails-26
Git hub repository from Team mebers :- P.Harsha datta,A.Naga koushtub,B.Balavignesh, Ananya Kavuri, K. Sahithi Reddy
#  AI-Powered Insurance Claim Verification System  
### DEVTrails 2026 — Phase 1 Submission  

**Parametric Insurance • Fraud Detection • Anti-Spoofing • Blockchain Settlement**

---
## 🚀 Problem Overview

Gig economy delivery partners lose up to 30% of their income due to uncontrollable events like floods, heavy rain, and curfews.

Existing insurance systems:
- ❌ Are slow  
- ❌ Require manual verification  
- ❌ Are vulnerable to fraud  

We solve this using:
- 👉 AI-driven real-time verification  
- 👉 Fraud-resistant architecture  
- 👉 Blockchain-backed transparency  

It is specifically designed to resist advanced adversarial attacks, including coordinated GPS spoofing syndicates.  

---


## 👤 Target Users

Our primary users are gig economy delivery partners working with platforms like:
- Swiggy
- Zomato
- Amazon
- Zepto

### Key Challenges Faced:
- Income loss during extreme weather
- No financial protection during curfews
- No trust in claim approval systems

Our system ensures:
- Instant financial protection
- Fair and transparent claim verification
## 🤖 How Our AI Works (Simple View)

Our system uses a multi-step AI validation pipeline:

1. 📥 Claim is submitted by user  
2. 🌍 AI Agent collects real-world data (weather + govt alerts)  
3. 📊 ML models analyze:
   - Location consistency
   - Movement behavior
   - Fraud patterns  
4. 🧠 NLP checks if user description matches real conditions  
5. ⚖️ Decision engine classifies:
   - ✅ Genuine claim  
   - ⚠️ Suspicious  
   - ❌ Fraud  

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

---


##** 💡 Core Innovation**

"We don’t trust location — we trust behavior."

Our system validates claims using behavioral patterns, environmental data, and multi-source verification instead of relying on easily spoofed GPS signals.
