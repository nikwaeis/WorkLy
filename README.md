# 🚀 Workly — Quick Job Search Platform

**Workly** is a high-speed platform designed to connect workers with immediate job opportunities. The system is optimized for low latency, rapid data processing, and a seamless cross-platform experience.

---

## 💡 Project Overview & Startup Pitch

In today's fast-paced world, finding a reliable temporary contractor or a quick gig shouldn't take days. **Workly** addresses the fragmented on-demand labor market by providing a near-instant matching ecosystem. 

Our platform enables clients to post jobs within seconds, while performers can locate nearby gigs immediately using an interactive map. We ensure trust and security for both parties through robust identity verification, escrow payment holds, and automated activity monitoring.

### Key Features:
* **Dual Profile (Role Switching):** Seamlessly toggle between "Client" and "Performer" modes instantly without logging out or managing multiple accounts.
* **Real-Time Job Feed & Map-Based Search:** A constantly updated chronological feed and GPS-centered map view to find jobs instantly and minimize travel times.
* **Flexible Pricing Models:** Support for both fixed pricing and open bidding (Price Counter-Offers) to match market expectations dynamically.
* **Secure Escrow Transactions:** Financial peace of mind via automated escrow fund reservation upon hiring, releasing payments only upon verified task completion.
* **Trust & Verification (KYC Level 2):** Secure identity verification using government-issued IDs and face matching to unlock high-budget orders.
* **Secure Communication & Visual Proof:** In-app encrypted messaging with real-time delivery, read receipts, and progress/final photo documentation.

---

## 🛠 Technical Architecture & Stack

The technical stack is selected specifically to maintain high throughput and type safety across the entire ecosystem:

| Layer | Technology | Role & Startup Justification |
| :--- | :--- | :--- |
| **Database** | PostgreSQL | Handles volatile real-time geographic data and concurrent job applications. Native Full-Text Search replaces heavy tools like Elasticsearch, and JSONB supports flexible metadata. |
| **ORM** | EF Core | Bridges C# business logic with the relational data layer with full type safety. |
| **Backend** | ASP.NET Core (Web API) | High-performance API powered by the Kestrel web server. Built using Minimal APIs and a Lean Service Layer (avoiding MediatR overhead) to keep the request pipeline lean and rapid. |
| **Frontend** | React (TypeScript) | Single Page Application (SPA) offering instant navigation, state hooks for real-time status updates ("Heading There", "Work Started"), and a mobile-first responsive layout. |
| **Admin Tooling** | System.CommandLine 2.0.1 | High-speed CLI utilities for system administrators to perform bulk maintenance, fraud prevention, and cache clearing directly from the terminal. |

---

## 📂 Repository & Documentation Structure

This repository functions as a comprehensive startup pitch and blueprint. The architectural documentation is organized inside the `docs/` directory:

* 📄 `README.md` — Main project introduction and startup overview.
* 📄 `docs/domain-model.md` — Domain Model detailing core Entities (`User`, `Order`, `Service`, `Category`, `Payment`, `Service Delivery`, `Review`) and their relational schema (1:N, N:1, 1:1).
* 📄 `docs/USE-CASES.md` — Thorough specification of 45 atomic Use Cases covering account setup, advanced matching, real-time tracking, escrow management, and dispute-ready logging.
* 📄 `docs/TECH-CHOICES.md` — Technical breakdown, architectural context, and detailed decisions for the stack components.
* 📄 `docs/REQUESTS.md` — Product discovery phase questionnaire tracking client integrations, university accounts, design guidelines, and scope definitions.
* 📄 `docs/DB_MODEL.md` — Database relational structure mapping domain properties to PostgreSQL tables.
* 📁 `docs/user-flow/` — Process logic visual charts (Excalidraw & exported SVG maps):
    * `USER-FLOW.md` — General overview of user journeys.
    * `Create-offer.svg` — Visual logic for offer creation, pricing format check, and verification validation.
    * `Registration.svg` — Flowchart representing double-layer format/database verification and token provisioning.
    * `SignIn(Start).svg` — Secure token lifecycle, token renewal, and brute-force protection logic (lockout after >3 bad requests).

---
*Developed and conceptualized by Team 2 as a startup initiative at Kazimierz Wielki University (Uniwersytet Kazimierza Wielkiego).*
