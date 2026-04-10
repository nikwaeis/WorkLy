# Tech Choices - Workly (Quick Job Search Platform)
This document outlines the technical architecture for Workly, a high-speed platform designed to connect workers with immediate job opportunities. The stack is optimized for low latency, rapid data processing, and a seamless cross-platform experience.

## Data Storage (PostgreSQL)
**Context:**
Workly handles high volumes of volatile data: job postings that appear and disappear quickly, real-time geographic locations, and user reputation systems.

**Decision:**
PostgreSQL.

**Justification:**

- Full-Text Search: Native support for high-performance searching across job descriptions without needing external tools like Elasticsearch.

- Concurrency: Excellent handling of row-level locking, which is critical when multiple users are trying to "claim" the same limited-time job.

- JSONB Support: Allows for flexible metadata in job postings (e.g., specific requirements for a delivery gig vs. a coding task) while keeping the core schema relational.

- Reliability: ACID compliance ensures that financial transactions and job contracts are never lost or duplicated.

## Backend Framework (ASP.NET Core)
**Context:**
The backend serves as the high-performance engine for Workly, handling job matching algorithms, notifications, and the primary REST API.

**Decision:**
ASP.NET Core (Web API).

**Justification:**

- High Throughput: Leveraging the Kestrel web server ensures the platform remains responsive even during peak hiring hours.

- Service-Oriented Architecture: By injecting services directly (avoiding the overhead of libraries like MediatR), we keep the request pipeline lean and the execution path transparent.

- Native Integration: Seamlessly works with EF Core and PostgreSQL (Npgsql) to provide a type-safe data layer.

- Security: Built-in support for JWT authentication and OAuth2 ensures worker and employer data stays protected.

## CLI Infrastructure (System.CommandLine)
**Context:**
Platform administrators need high-speed tools for system maintenance, such as bulk-suspending fraudulent accounts or cleaning up expired job listings.

**Decision:**
System.CommandLine (Version 2.0.1).

**Justification:**
- To ensure the administrative experience is as fast as the app itself, we use version 2.0.1 of the library. It allows us to:

- Rapid Scripting: Create complex admin commands with typed parameters for database maintenance.

- Efficiency: Perform "under-the-hood" operations (like re-indexing or cache clearing) directly from the terminal without a GUI.

- Standardization: Provides a consistent, professional interface for developers managing the Workly ecosystem on their devices.

## Frontend (React)
**Context:**
The user interface for "Quick Jobs" must be near-instant. Users need to swipe, filter, and apply for jobs in seconds.

**Decision:**
React with TypeScript.

**Justification:**

- Single Page Application (SPA): Once loaded, navigating between "Search," "Applied Jobs," and "Profile" is instantaneous, which is vital for a "quick work" app.

- Real-time Updates: React’s state management (via Hooks) makes it easy to reflect job status changes (e.g., "Position Filled") in real-time without refreshing.

- Rich Ecosystem: Large library of UI components for maps, calendars, and drag-and-drop features, significantly speeding up the development cycle.

- Mobile-First Design: Easy to optimize for mobile browsers or wrap into a PWA (Progressive Web App) for users searching for work on the go.

## Summary Table
| Layer |	Technology |	Role in Workly |
| :-- | :-- | :-- |
| Database |	PostgreSQL |	Managing jobs, users, and real-time matching. |
| ORM |	EF Core |	Bridging C# logic with the relational database. |
| Backend |	ASP.NET Core |	High-performance API (Lean Service Layer). |
| Admin Tooling |	System.CommandLine 2.0.1 |	High-speed CLI management utilities. |
| Frontend |	React (TS) |	Fast, responsive UI for job seekers. |
