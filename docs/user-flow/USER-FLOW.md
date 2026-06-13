# 🗺️ Workly — User Flow Specification

This document provides a detailed overview of the core user flows and behavioral diagrams implemented across the Workly platform ecosystem. These flows map user interactions from the frontend directly to backend validation pipelines and data access layers.

---

## 📋 Table of Schemes

1. [User Registration Flow (`Registration.svg`)](#1-user-registration-flow-registrationsvg)
2. [User Authentication & Token Lifecycle (`SignInStart.svg`)](#2-user-authentication--token-lifecycle-signinstartsvg)
3. [Offer Creation & Verification Verification (`Create-offer.svg`)](#3-offer-creation--verification-verification-create-offersvg)

---

## 1. User Registration Flow

This diagram describes the secure, multi-tier account onboarding pipeline, ensuring data format integrity and platform uniqueness constraints.

* **File Link:** [Registration.svg](./Registration.svg)
* **Core Stages:**
  * **First-Level Validation (Client-Side & Pipeline):** Validates precise string formatting (RFC-compliant emails, international phone number criteria, and required password complexity blocks).
  * **Second-Level Validation (Data Layer):** Performs non-blocking database queries to check unique constraints against existing records (`Email` and `Nickname`).
  * **Account Provisioning:** Commits the transaction to PostgreSQL, instantiates a default account with **Verification Level 1** access privileges, and initiates the email verification process.
  * **Token Handshake:** Generates and securely transmits the initial cryptographically signed JSON Web Token (JWT) key pair to the client device.

---

## 2. User Authentication & Token Lifecycle

This diagram covers standard login logic, brute-force protection mechanisms, and seamless automated session prolongation.

* **File Link:** [SignIn(Start).svg](./SignIn(Start).svg)
* **Core Stages:**
  * **Credential Verification:** Matches user-supplied identifiers against cryptographic password hashes stored securely within the database.
  * **Security Gate (Brute-Force Lockout):** Tracks failed login attempts sequentially. Upon reaching a threshold of `> 3` failed requests, the system triggers a dynamic rate-limiting barrier, blocking attempts and enforcing a 5-10 minute cooldown window.
  * **Session Initialization:** Issues fresh Access and Refresh token pairs upon successful authorization.
  * **Token Maintenance Cycle:** The frontend app implicitly evaluates token states:
    * *Access Token Active:* Seamless resource consumption via secured REST API routes.
    * *Access Token Expired / Refresh Token Active:* Triggers an silent background handshake to regenerate a new access key and cycle the refresh token without disrupting user interaction.
    * *Both Tokens Expired:* Safely flushes the client cache and redirects the user back to the primary authentication page.

---

## 3. Offer Creation & Verification Verification

This diagram structures the sequential form validation required to publish a task, combined with an advanced check for trusted user metrics.

* **File Link:** [Create-offer.svg](./Create-offer.svg)
* **Core Stages:**
  * **Authentication Guard:** Verifies the presence of a valid, live active session token before exposing the form.
  * **Field Validation Loop:**
    * **Title Content:** Blocks submission if empty; triggers localized string errors.
    * **Temporal Expiry constraint:** Enforces a logical strict comparison ensuring chosen deadline targets are explicitly set in the future (`> DateTime.Now`).
    * **Geospatial Coordinates:** Validates that precise GPS pin placement or address autocomplete metadata is bundled with the request.
    * **Price Matrix:** Confirms a valid positive numerical currency format is present, adjusting based on whether the chosen layout is "Fixed Price" or "Open for Offers".
  * **Startup KYC Trust Layer:** Queries the backend to evaluate if the client possesses **Verification Level 2 (KYC)**.
    * *If Level 2 Verified:* Enhances the offer payload with explicit worker criteria boundaries (headcount, age gates) and affixes a global high-visibility "Verified User" trust badge.
    * *If Level 1 Only:* Appends a baseline unverified flag, rendering the offer under standard visibility constraints.

---
*Document Version: 1.0.0 — Workly Architectural Documentation Blueprint.*
