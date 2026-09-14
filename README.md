<h1 align="center">Wyatt Flewelling</h1>

<p align="center">
  <b>Biomedical Engineering · University of Wisconsin–Madison ’27</b><br>
  Bioinstrumentation &amp; medical devices — from the analog front end to the app that reads it.
</p>

<p align="center">
  <a href="https://linkedin.com/in/wyatt-flewelling">LinkedIn</a> ·
  <a href="mailto:wyattflew@yahoo.com">Email</a> ·
  Chicago, IL
</p>

---

I build measurement systems for the human body. That usually means the whole stack: a custom PCB and analog front end, embedded firmware streaming over BLE, the signal conditioning that separates real physiology from motion artifact, and the iOS app a clinician or patient actually touches.

Right now I'm a senior at Wisconsin doing bioinstrumentation and medical devices, working part-time in QA/QC and commissioning engineering, and shipping small iOS apps on the side to keep the software half sharp.

**Currently:** senior capstone design · Medical Instrumentation · Electronic Circuits I

---

## Featured work

### 🩺 Pavlik Harness Kick Sensor — wearable EMG for infant femoral nerve palsy
`Nordic nRF54L15` · `Zephyr RTOS` · `Embedded C` · `custom PCB` · `Swift` · `Kotlin` · `Firebase`

Femoral nerve palsy in infants treated with a Pavlik harness is normally screened on hospital EMG equipment, which means the diagnostic delay is measured in days. This moves the screen to a wearable.

Three channels at 1 kHz each over BLE, on a board I designed from schematic through layout. The hard part wasn't the sampling — it was that infants move constantly, so the muscle signal arrives buried in motion artifact. I implemented **Teager–Kaiser Energy Operator** conditioning to isolate activation, which improved detection accuracy by 35%, then cross-validated the whole chain against a **Noraxon Ultium** clinical EMG system to characterize the ADC-resolution, sample-rate, and BLE-timing trade-offs.

Native iOS and Android clients handle the BLE central role, live waveform rendering, Face ID auth, and HIPAA-aware PHI handling over TLS.

The firmware and Android client are public in [`emg-wearable-platform`](https://github.com/wcflewelling/emg-wearable-platform); the iOS client and the clinical framing stay private.

---

### 💪 MyoSense — sEMG biofeedback platform
`Swift/SwiftUI` · `CoreBluetooth` · `Zephyr RTOS` · `custom PCB`

The same sensing platform pointed at rehab and training instead of the clinic: dual-channel surface EMG with real-time muscle-activation visualization, bilateral comparison, a TKEO activation classifier, and CSV export for anyone who wants the raw data. Runs in a demo mode with synthetic signal when no hardware is attached.

Deliberately positioned as **research and educational use, not a medical device** — the regulatory path for a cleared device is a different project entirely, and pretending otherwise would be dishonest to users.

Shares the sensing stack in [`emg-wearable-platform`](https://github.com/wcflewelling/emg-wearable-platform).

---

### 🔐 Passport AI — signed, revocable credentials for AI agents
`Swift` · `ES256 / JWT` · `Secure Enclave` · `Cloudflare Workers`

Issues cryptographically signed permission credentials to AI agents and verifies them **statelessly** — a verifier checks a token without calling back to the issuer. Private keys never leave the iOS Secure Enclave; issuance is gated behind Face ID.

Also ships the part most token systems skip: **revocation**. A KV-backed revocation list lets an issued credential be killed immediately, with the verify endpoint failing closed on a bad token and the gateway refusing to create an order rather than failing open. Verify, gateway, and middleware suites all green.

**Live on the App Store** for iOS and macOS.

---

### 📅 Slotted — calendar-aware training scheduler
`Swift/SwiftUI` · `EventKit` · `StoreKit 2` · `HealthKit`

Reads your real calendar and turns the gaps into a training plan — when to lift, eat, hydrate, and wind down. **Privacy-first as a hard constraint:** no servers, no accounts, no analytics, no third-party SDKs. Everything stays on device, which is also why the App Store privacy label reads "Data Not Collected" honestly.

**Live on the App Store.**

---

### 🍽️ Phone Eats First — social meal logging
`Swift/SwiftUI` · `SwiftData` · `Firebase`

Friends-only meal photo feed with streaks. No algorithm, no ads, no public timeline. Anonymous Firebase Auth means zero signup friction.

**Live on the App Store.**

---

### 🖼️ Apple Photos MCP
`Python` · `Model Context Protocol`

A local MCP server exposing the macOS Photos library to AI assistants — nine tools for search, album management, and export. Runs entirely on-device; no photos leave the machine.

*Source private.*

---

## Experience

**Apollo Mission Critical Engineering** — QA/QC & Cx Engineering Intern · *May 2026 – present*
Commissioning across concurrent data center buildouts. Built a Python report-generation pipeline (Excel → Word) that cut weekly QA/QC status reporting from a multi-hour manual process to roughly one command, and scaled an inspection tracker from a 78-item pilot to a 4,185-line-item portfolio standard.

**ANI Pharmaceuticals** — Quality Engineering Intern · *Jun – Aug 2025*
Defect inspection and root-cause analysis across 24,000+ Class II medical device kits in ISO 13485 cleanrooms. Built a batch traceability protocol that cut inspection review time 50%.

**Morgridge Institute for Research** — Undergraduate Research Assistant · *Aug 2024 – Aug 2026*
Python image-analysis pipelines for optical metabolic imaging; quantified NADH/FAD redox shifts in infected colorectal cancer organoids. Mentored 10+ students.

---

## Toolbox

**Languages** Python · Swift/SwiftUI · C/C++ · MATLAB · Java
**Embedded** Zephyr RTOS · Embedded C · BLE · Nordic nRF54L15 · PCB design (schematic → layout) · analog front-end &amp; filter design · DSP / signal conditioning
**Platforms** Xcode · Firebase/Firestore · Cloudflare Workers · Git · LTSpice · SolidWorks · Onshape · 3D printing · MTS load-frame testing
**Standards** ISO 13485 · FDA 21 CFR 820 · IEC 60601 · GMP · Design Controls · Verification &amp; Validation
**Lab** Sterile organoid culture · PCR genotyping · gel electrophoresis · optical metabolic imaging
**Certifications** NFPA 70E · OSHA 30 · CPR/AED/First Aid

---

<p align="center"><sub>Bilingual (Spanish/English) · Dean's List, four semesters · GPA 3.64</sub></p>
