# Thrive Camp Setu — Digital Health Camp Management System

A digital forms and records management prototype built for **Thrive Camp**, a clinical health screening initiative at **IIT Kharagpur**, run in collaboration with the **Setu** campus platform.

This prototype was designed during an internship to replace paper-based patient intake at health camps with a clean, fast, tablet-friendly digital workflow — covering patient consent, post-visit feedback, record-keeping, and a live public display screen.

---

## What This Prototype Does

Health camps at IIT Kharagpur run clinical screenings (hemoglobin, glucose, oral health, etc.) and need to:

1. Collect **informed consent** from each patient before screening
2. Collect **post-visit feedback** to measure patient experience
3. Maintain a searchable, exportable **record of every patient** registered
4. Display **live feedback** on a secondary monitor at the camp for transparency and engagement
5. Continue working **with intermittent or no internet**, since camps are often held in locations with poor connectivity

This prototype addresses all five needs in a single, unified interface.

---

## Core Screens

### 1. Consent Form
A guided 4-step form for capturing informed patient consent before a clinical screening:
- **Study Identifiers** — Setu ID, Patient ID, Device/Study Type
- **Patient Details** — name, age, gender, contact information
- **Declarations** — itemized consent checkboxes the patient must agree to
- **Signatures** — digital signature capture for both patient/guardian and staff

The stepper visually tracks progress, with completed steps marked and a live progress bar.

### 2. Feedback Form
A short post-visit survey covering:
- Satisfaction with the screening process
- Clarity of explanation
- Comfort and privacy
- Whether the screening improved health understanding
- Open-ended comments

Ratings use a 1–5 scale with clear "low" and "high" anchor labels on each end.

### 3. Patient Records
A searchable, sortable dashboard of all registered patients, including:
- Summary stat cards (Total Patients, Male, Female, Registered Today)
- A live search bar (by name, Setu ID, or Patient ID)
- A clean data table with alternating rows
- **CSV export** for offline reporting and analysis
- A friendly empty state when no patients are registered yet

### 4. Drafts
Supports **offline-first data entry** — if a consent form can't be submitted (no network), it's automatically saved as a draft locally. From the Drafts screen, staff can:
- **Resume** an incomplete form exactly where they left off (all fields restored)
- **Delete** unwanted drafts
- **Sync All** drafts to Patient Records in one action once back online

An offline banner and a "back online" toast keep staff informed of connectivity status in real time.

### 5. Display Screen
A live, public-facing view (meant for a secondary monitor at the camp) that mirrors the most recently submitted feedback — Setu ID, Patient ID, satisfaction scores, and written comments — updating instantly as new feedback comes in.

---

## Design System

The interface follows the **Setu** brand identity used across IIT Kharagpur's campus platform:

| Element | Value |
|---|---|
| Primary accent | `#E63946` (Setu red) |
| Sidebar background | `#1A1A2E` |
| Page background | `#F5F6FA` |
| Font | Inter |
| Card style | White, rounded corners, soft shadow |

The sidebar is organized into three logical groups — **Forms**, **Records**, and **Display** — with a persistent sync status and account indicator at the bottom.

---

## Key UX Decisions

- **Offline resilience** — Forms can be saved as drafts and resumed later, so staff never lose patient data due to a dropped connection.
- **Step-based consent flow** — Breaking the consent form into 4 steps (rather than one long form) reduces cognitive load for both patients and staff during fast-paced camp registration.
- **Immediate feedback loop** — The live Display Screen gives camp organizers real-time visibility into patient sentiment without needing to check the dashboard.
- **Familiar patterns for non-technical staff** — Large touch targets, clear labels, and minimal jargon make the tool usable by camp volunteers with no prior software training.

---

## Status

This is a **frontend prototype** — built to validate the design and interaction flow before backend integration. Data is currently stored locally in the browser (`localStorage`) to simulate persistence for demo purposes.

### Next Steps for Production
- Connect to a real backend/database for patient records and sync
- Add authentication for staff accounts
- Real-time sync (e.g. WebSockets) for the Display Screen instead of local storage polling
- Role-based access (e.g. admin vs. on-ground staff)

---

## Tech Stack

- HTML / CSS / JavaScript (no framework dependencies)
- Designed and iterated using Google Stitch and manual refinement
- Built as part of an internship project at IIT Kharagpur (Thrive Camp × Setu)
