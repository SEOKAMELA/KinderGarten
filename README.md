# KinderGarten Platform

**Copyright © 2025 Biko Today. All Rights Reserved.**
This software is a proprietary system built for Biko Today clients.
Unauthorized copying, modification, or distribution is prohibited.

[![Built With](https://img.shields.io/badge/built%20with-Frappe%2FERPNext-blue)]()

The **KinderGarten Platform** is a school management system designed to unify **communication, learning records, billing, and administration** into a single, secure, digital ecosystem.
Built with **Frappe + ERPNext**, the platform is tailored for South African schools and fully **POPIA-compliant**, offering parents, teachers, and administrators a seamless experience.

---

## Table of Contents

* [Features](#features)
* [Technology Stack](#technology-stack)
* [Architecture Overview](#architecture-overview)
* [Quick Start](#quick-start)
* [Contributing](#contributing)
* [License](#license)
* [Security & Compliance](#security--compliance)

---

## Features

* **Communication Hub**: Announcements, newsletters, WhatsApp updates
* **Accounts & Billing**: Fee structures, invoices, payments, and receipts
* **Child Journey**: Student profiles, academic progress, reports, and media
* **Extra-Murals & Aftercare**: Club registration, attendance tracking, and billing automation
* **Fundraising & Merch**: Donations, raffles, and merchandise management
* **Wallet & Vouchers**: Parent digital wallets, top-ups, and QR redemption
* **Resources & Service Providers**: Curated educational content and local services
* **Lifetime Profile**: Alumni and archival student records

---

## Technology Stack

| Layer          | Technology                        | Purpose                                                |
| -------------- | --------------------------------- | ------------------------------------------------------ |
| Backend Core   | Frappe + ERPNext                  | Manages students, guardians, fees, events, and reports |
| Frontend       | Next.js PWA + Flutter Mobile Apps | Responsive parent and teacher portal                   |
| Database       | MariaDB                           | Structured storage for ERPNext and Frappe apps         |
| Storage        | Wasabi / AWS S3                   | Media files (photos, videos, reports)                  |
| Authentication | Firebase / Keycloak               | Secure login and single sign-on                        |
| Payments       | PayFast / Paystack / Yoco         | Fee collection, wallet top-ups, event payments         |
| Messaging      | WhatsApp Business API             | Automated and manual communications                    |
| Automation     | n8n / Make.com                    | Notifications, reminders, and event triggers           |

---

## Architecture Overview

The platform follows a layered architecture:

* **Backend Core**: ERPNext + Frappe manage all school data, academic records, and billing.
* **Frontend Layer**: Next.js PWA for web users and Flutter apps for mobile parents and teachers.
* **Integration Layer**: Payment gateways, messaging APIs, and automation workflows.
* **Storage & Database**: MariaDB for structured data, AWS/Wasabi for media.
* **Authentication & Security**: Firebase/Keycloak for SSO, role-based access control, and consent management.

---

## Quick Start

### Prerequisites

* Python 3.10+
* Node.js 18+
* MariaDB 11.3+
* Redis 6+
* Yarn
* Frappe & ERPNext v15

### Installation Steps

```bash
# 1. Clone the repository
git clone git@github.com:SEOKAMELA/KinderGarten.git
cd KinderGarten

# 2. Initialize a new bench
bench init kindergarten-bench --frappe-branch version-15

# 3. Create a new site
bench new-site kindergarten.localhost

# 4. Get ERPNext and Education modules
bench get-app erpnext --branch version-15
bench get-app education --branch version-15

# 5. Get custom app from GitHub
bench get-app https://github.com/SEOKAMELA/KinderGarten.git

# 6. Install apps
bench --site kindergarten.localhost install-app erpnext
bench --site kindergarten.localhost install-app education
bench --site kindergarten.localhost install-app biko_kindergarten

# 7. Start development server
bench start
```

### Notes

* Always install ERPNext before Education and custom apps.
* Use `bench migrate` after pulling changes to update the database schema.
* Do not push the entire bench; only push custom apps.

---

## Contributing

This app uses `pre-commit` for code formatting and linting. Please [install pre-commit](https://pre-commit.com/#installation) and enable it for this repository:

```bash
cd apps/biko_kindergarten
pre-commit install
```

Pre-commit is configured with:

* ruff
* eslint
* prettier
* pyupgrade

Follow coding standards and ensure all new code passes pre-commit checks before pushing.

---

## License

MIT

---

## Security & Compliance

* Fully POPIA-compliant for South African schools.
* Role-based access control for students, parents, teachers, and admins.
* Secure authentication with Firebase/Keycloak.
* Encrypted storage for sensitive student and financial data.
