# MediTrack — Smart Medication Management System

A full-stack, multi-role platform for medication adherence monitoring, combining IoT hardware sensing with a web dashboard and companion mobile app. Built as a final-year Computer Science dissertation project at De Montfort University (CTEC3451).

## Why this project

Medication non-adherence is a widespread problem in healthcare, especially for patients managing multiple prescriptions or relying on caregivers for support. MediTrack explores how low-cost IoT hardware and a role-based software platform can close that gap — giving patients a simple way to track doses, caregivers visibility into adherence patterns, and doctors a clinical view of patient compliance.

## What it does

MediTrack supports three distinct user roles, each with a purpose-built dashboard:

- **Patient** — views medication schedule, logs doses, sees adherence history
- **Caregiver** — monitors one or more patients, receives adherence alerts, reviews trends
- **Doctor** — reviews patient compliance data to inform clinical decisions

Dose events are captured at the hardware level using an ESP8266 microcontroller connected to a magnetic reed switch (pill box open/close detection) and a load cell with HX711 amplifier (weight-based pill count verification), and streamed to a Flask backend for processing and storage.


## Tech stack

| Layer | Technology |
|---|---|
| Hardware | ESP8266 NodeMCU, magnetic reed switch, HX711 load cell amplifier |
| Backend | Python (Flask), REST API |
| Database | PostgreSQL |
| Frontend | HTML, CSS, JavaScript (vanilla, role-based dashboards) |
| Mobile | Flutter |

## Features

- Role-based authentication and dashboards (patient / caregiver / doctor)
- Real-time dose-event capture from physical hardware
- Adherence history and trend visualisation
- Caregiver-to-patient linked monitoring
- Cross-platform access via web dashboard and native mobile app

## Getting started

### Prerequisites
- Python 3.x
- PostgreSQL
- Node/Flutter SDK (for mobile app)
- ESP8266-compatible hardware (optional — required only for live sensor data; the platform runs standalone against seeded/demo data otherwise)

### Backend setup
```bash
git clone https://github.com/<your-username>/meditrack.git
cd meditrack
pip install -r requirements.txt

# Configure PostgreSQL connection in config
# Create the database
createdb smart_medication_db

python app.py
```

### Demo access
The project includes seeded demo accounts for each role so the platform can be explored without hardware:

| Role | Email |
|---|---|
| Patient | `patient@meditrack.demo` |
| Caregiver | `caregiver@meditrack.demo` |
| Doctor | `doctor@meditrack.demo` |


## What I'd build next

- Full reed switch / load cell sensor integration end-to-end
- Push notifications for missed doses
- Doctor-facing analytics and scenario tooling
- Automated testing across the Flask API and dashboards

## Author

**Kowthar Abdiqadir**

https://www.linkedin.com/in/kowthar-abdiqadir/ · kowthar.abdiqadir@outlook.com 
