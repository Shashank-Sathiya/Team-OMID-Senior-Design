# User Stories and Use Cases

**Team Members:** Shashank Sathiyanarayanan, Arleen Monteiro, Jaxon Polo, Kyle Russell, Nyla Spencer  
**Project Name:** Team OMID — Transparent Organic Photovoltaics (OPVs) for Agricultural Energy Generation  
**Repository Tag:** `week04`

---

## 1. Stakeholder Map

Our team identified stakeholders across three categories using elicitation techniques (interviews with agricultural advisors, literature reviews, and technical constraint analyses):

*   **Primary Stakeholders (Direct Users):** 
    *   *Role:* **Agribusiness Farm Manager** — Directly monitors real-time energy generation dashboards, crop light transmission ratios, and daily microgrid performance via the management portal.
*   **Secondary Stakeholders (Support / Operations):** 
    *   *Role:* **Field Installation and Maintenance Technician** — Deploys hardware nodes, troubleshoots physical OPV panel wiring, and handles physical hardware diagnostics.
*   **Hidden Stakeholders (Downstream / Compliance / Security):** 
    *   *Role:* **Agricultural Microgrid Compliance Inspector** — Evaluates adherence to IEEE 1547 standards governing distributed energy resources interconnecting with local agricultural microgrids.
    *   *Role:* **System Security Administrator** — Manages cryptographic keys, AES-128 encryption protocols, and network access boundaries to protect proprietary telemetry from unauthorized access.

---

## 2. User Stories (US-01 to US-04)

*   **US-01 (Primary):** As an agribusiness farm manager, I want to view aggregated daily energy yields and photosynthetically active radiation (PAR) levels on a single dashboard, so that I can optimize crop growth while tracking solar power generation.
*   **US-02 (Secondary):** As a field installation and maintenance technician, I want to receive automated diagnostic alerts when a transparent OPV panel's power output drops below expected efficiency thresholds, so that I can rapidly locate and service faulty hardware.
*   **US-03 (Hidden):** As an agricultural microgrid compliance inspector, I want the system to automatically generate exportable compliance logs verifying adherence to IEEE 1547 interconnection safety limits, so that the farm can legally operate its distributed energy resources.
*   **US-04 (Hidden):** As a system security administrator, I want all wireless telemetry transmissions between field nodes and the central server to be secured with AES-128 encryption, so that operational energy statistics cannot be intercepted by malicious actors.

### INVEST Self-Check
*   **Independent:** Yes, stories can be developed and tested in separate modules (e.g., dashboard data visualization vs. cryptographic packet encryption).
*   **Negotiable:** Yes, implementation details (such as UI chart libraries or specific database schemas) remain open for design iteration.
*   **Valuable:** Yes, every story delivers direct, verifiable value to a distinct stakeholder category.
*   **Estimable:** Yes, technical complexity and scope have been sized by the development team.
*   **Small:** Yes, each story is scoped to fit within a standard sprint delivery cycle.
*   **Testable:** Yes, all criteria feature objective, measurable outcomes and clear states.
*   *Note on UI Elements:* No stories contain UI implementation mandates (e.g., "dropdown menu" or "red button"); they focus entirely on user goals and benefits.

---

## 3. Use Cases

### UC-01: Monitor Real-Time Energy Yield and Crop Light Transmission
*   **Expands Story:** US-01
*   **Primary Actor:** Agribusiness Farm Manager
*   **Secondary Actors:** Field Sensor Nodes, Central Database
*   **Preconditions:** 
    1. The farm manager has an active, authenticated account with administrative permissions.
    2. Transparent OPV field sensor nodes are deployed and actively streaming telemetry over the encrypted network.

#### Main Success Flow
1. Farm manager logs into the OMID management portal using valid credentials.
2. System authenticates user and displays the main dashboard overview.
3. Farm manager navigates to the "Energy & PAR Analytics" view and selects a specific greenhouse zone.
4. System queries the central database and retrieves real-time power generation data and visible light transmission metrics.
5. System renders the aggregated energy yield graphs and transmission percentages on the dashboard within **1.5 seconds**.

#### Alternate Flow (A1: Historical Data Range Selected)
*   *At step 3:* If the farm manager selects a custom historical date range instead of real-time view, the system aggregates historical records from the database and renders the trend chart within **2.0 seconds**.

#### Exception Flow (E1: Database Connection Timeout)
*   *At step 4:* If the central database fails to respond within **3.0 seconds** due to a network interruption:
    1. System intercepts the timeout error.
    2. System aborts data rendering and displays an inline notification banner: *"Unable to retrieve live telemetry. Displaying last cached data from 10 minutes ago."*
    3. System renders the most recent cached telemetry payload to ensure operational continuity.

#### Postconditions
*   **Success:** The farm manager successfully views up-to-date energy yields and light transmission metrics without system errors.
*   **Failure:** The dashboard falls back to cached data, displays a clear notification banner, and logs the database connection timeout for system administrators.

---

## 4. Acceptance Criteria (Given / When / Then)

*   **AC-01.1 (Main Success Flow Criterion):**
    *   **Given** an authenticated farm manager viewing the OMID management portal,
    *   **When** the manager selects a specific greenhouse zone for real-time monitoring,
    *   **Then** the system must render the energy yield and PAR light transmission graphs within **1.5 seconds**.

*   **AC-01.2 (Exception Flow Criterion):**
    *   **Given** an authenticated farm manager requesting telemetry data while the central database is unresponsive,
    *   **When** the database query times out after **3.0 seconds**,
    *   **Then** the system must display an error notification banner and load cached telemetry data without crashing the dashboard interface.
