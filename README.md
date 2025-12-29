# KinderGarten Platform

[![License](https://img.shields.io/badge/license-MIT-green)](LICENSE) [![Built With](https://img.shields.io/badge/built%20with-Frappe%2FERPNext-blue)]()

The **KinderGarten Platform** is a comprehensive school management system designed to unify communication, learning records, billing, and administration into a single, secure, digital ecosystem.  
Built with **Frappe + ERPNext**, the platform is tailored for South African schools and fully **POPIA-compliant**, offering parents, teachers, and administrators a seamless experience.

---

## Table of Contents

- [Features](#features)  
- [Technology Stack](#technology-stack)  
- [Architecture Overview](#architecture-overview)  
- [Quick Start](#quick-start)  
- [Project Status](#project-status)  
- [Security & Compliance](#security--compliance)  
<!-- - [Delivery Timeline](#delivery-timeline) -->  
<!-- - [Contribution](#contribution) -->  
- [License](#license)  
<!-- - [Contact](#contact) -->  

---

## Features

- **Communication Hub**: Announcements, newsletters, WhatsApp updates  
- **Accounts & Billing**: Fee structures, invoices, payments, and receipts  
- **Child Journey**: Student profiles, academic progress, reports, and media  
- **Extra-Murals & Aftercare**: Club registration, attendance tracking, and billing automation  
- **Fundraising & Merch**: Donations, raffles, and merchandise management  
- **Wallet & Vouchers**: Parent digital wallets, top-ups, and QR redemption  
- **Resources & Service Providers**: Curated educational content and local services  
- **Lifetime Profile**: Alumni and archival student records  

---

## Technology Stack

| Layer | Technology | Purpose |
|-------|------------|---------|
| Backend Core | Frappe + ERPNext | Manages students, guardians, fees, events, and reports |
| Frontend | Next.js PWA + Flutter Mobile Apps | Responsive parent and teacher portal |
| Database | MariaDB | Structured storage for ERPNext and Frappe apps |
| Storage | Wasabi / AWS S3 | Media files (photos, videos, reports) |
| Authentication | Firebase / Keycloak | Secure login and single sign-on |
| Payments | PayFast / Paystack / Yoco | Fee collection, wallet top-ups, event payments |
| Messaging | WhatsApp Business API | Automated and manual communications |
| Automation | n8n / Make.com | Notifications, reminders, and event triggers |

---

## Architecture Overview

The platform follows a layered architecture:

- **Backend Core**: ERPNext + Frappe manage all school data, academic records, and billing.  
- **Frontend Layer**: Next.js PWA for web users and Flutter apps for mobile parents and teachers.  
- **Integration Layer**: Payment gateways, messaging APIs, and automation workflows.  
- **Storage & Database**: MariaDB for structured data, AWS/Wasabi for media.  
- **Authentication & Security**: Firebase/Keycloak for SSO, role-based access control, and consent management.  

---

## Quick Start

### Prerequisites

- Python 3.10+  
- Node.js 18+  
- MariaDB 11.3+  
- Redis 6+  
- Yarn  
- Frappe & ERPNext v15  

### Installation Steps

```bash
# Clone repository
git clone <repo-url>
cd kinderGarten-platform

# Initialize bench
bench init kindergarten-bench --frappe-branch version-15

# Create a new site
bench new-site kindergarden.localhost

# Install ERPNext app
bench get-app erpnext --branch version-15
bench --site kindergarden.localhost install-app erpnext

# Start development server
bench start
