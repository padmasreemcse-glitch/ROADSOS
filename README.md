# 🚨 RoadSOS: Real-Time Emergency Telemetry & Dispatch Hub

RoadSOS is an intelligent emergency response console designed to empower vulnerable or stranded motorists during vehicle breakdowns and accidents. With a single click, users broadcast their identity and live GPS coordinates to a central database while tracking the proximity of critical assets like hospitals, ambulances, and puncture repair services.

---

## 💡 Project Description & Problem Solved
During a roadside emergency, high stress makes it incredibly difficult for motorists to accurately communicate their geographic coordinates. Valuable time is wasted navigating legacy phone hotlines or manually searching maps while device batteries drain. 

**RoadSOS** bridges this gap by creating a zero-friction, one-click crisis broadcast dashboard. It captures raw device telemetry, logs it instantly to a persistent ledger, and provides an end-to-end orchestration command center for automated dispatch.

---

## 🤖 UiPath Components Used
To orchestrate and automate the incident dispatch lifecycle, this solution leverages the following core ecosystem tools within the **UiPath Labs Environment**:
* **UiPath Maestro (Orchestrator):** Serves as the central command node to monitor active backend incoming telemetry feeds from the `/api/db-live-monitor` data stream.
* **UiPath Agent Builder:** Used to define the cognitive properties, rules, and triggers for dispatching rescue assets once a crisis telemetry point hits the database.
* **API Workflows:** Used to read real-time data from the Flask API nodes and securely forward automated instructions directly to designated dispatch personnel.

---

## ⚙️ Agent Type
* **Type:** **Low-code Agents** integrated with custom API endpoints. 
The system relies on declarative low-code business workflows within the UiPath platform to monitor the database state, combined with dynamic custom scripting to handle the underlying mathematical spatial calculations.

---

## 🚀 Setup & Execution Instructions for Judges

### 1. Repository Setup & Dependencies
```bash
# Clone the repository
git clone [https://github.com/YOUR_USERNAME/roadsos-emergency-dashboard.git](https://github.com/YOUR_USERNAME/roadsos-emergency-dashboard.git)
cd roadsos-emergency-dashboard

# Create and activate environment
python -m venv venv
source venv/bin/activate  # On Windows use: venv\Scripts\activate

# Install required frameworks
pip install flask flask-cors flask-sqlalchemy
2. Launching the Telemetry Hub
Bash
python app.py
The server will initialize locally at http://127.0.0.1:5001/ and dynamically create a fresh, clean schema instance of roadsos.db.

3. Evaluating the Solution Workflow
Open http://127.0.0.1:5001/ in your browser.

Ensure browser location permissions are granted so the W3C Geolocation API can lock onto your node.

Click 🚨 BROADCAST SOS ALERT.

Observe the live console: the data is successfully parsed into the Active Dashboard Monitor and outputted via the Database Row Audit Stream JSON feed, ready for the UiPath Maestro monitoring loop to trigger downstream automations.


---

UIPATH STUDIO LINK: https://cloud.uipath.com/roadsos/DefaultTenant/orchestrator_/

