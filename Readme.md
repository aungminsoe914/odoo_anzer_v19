# GTS Anzer Odoo Integration

## Overview

**GTS Anzer Odoo Integration** is a custom module developed by **Glow Together Solutions Co., Ltd** to integrate external **Anzer accounting codes** with the Odoo Accounting system.

This module allows synchronization and mapping of **Anzer financial codes** with Odoo accounting elements such as:

* Chart of Accounts
* Journals
* Taxes
* Accounting Entries
* Products
* Contacts

The module ensures seamless financial data integration between **Anzer system** and **Odoo 19**.

---

# Module Flow

### 1. External System (Anzer)

External accounting data is generated in the **Anzer system**.

Example:

* Account Codes
* Journal Entries
* Tax Codes
* Customer Codes

↓

### 2. Integration Layer (This Module)

The module processes and maps incoming data.

Main Models:

* Integration Configuration
* Integration Lines
* Mapping Tables

↓

### 3. Data Mapping

Anzer codes are mapped to Odoo records:

| Anzer Code    | Odoo Model      |
| ------------- | --------------- |
| Account Code  | account.account |
| Tax Code      | account.tax     |
| Journal Code  | account.journal |
| Customer Code | res.partner     |
| Product Code  | product.product |

↓

### 4. Odoo Accounting

Mapped records create or update:

* Journal Entries
* Accounting Moves
* Tax Records
* Contacts
* Products

↓

### 5. Reporting

All integrated data becomes available inside:

* Accounting Dashboard
* Financial Reports
* General Ledger
* Trial Balance

---

# Installation Guide

## 1. Clone Module from Git Repository

Login to your server.

Example server path:

```
/home
```

Clone the repository:

```bash
cd /home
git clone https://github.com/aungminsoe914/odoo_anzer_v19.git
```

---

## 2. Move Module into Odoo Addons Directory

Example:

```bash
mv anzer_odoo_integration /home/odoo/addons/
```

OR if using custom addons path:

```bash
mv anzer_odoo_integration /home/odoo/customaddons/
```

---

# Docker Deployment (Odoo 19)

If you are running Odoo using Docker, restart the container after adding the module.

Example:

```bash
docker restart odoo
```

Or if using docker-compose:

```bash
docker compose restart
```

You can check running containers:

```bash
docker ps
```

---

# Activate Module in Odoo

Open Odoo in your browser.

Example:

```
http://SERVER-IP:8069
```

Steps:

1. Login as Administrator
2. Go to **Apps**
3. Click **Update Apps List**
4. Search for:

```
GTS Anzer Odoo Integration
```

5. Click **Install**

The module will now be activated.

---

# Configuration

After installation:

Go to:

```
Accounting → Configuration → Anzer Integration
```

Setup:

* Anzer API Endpoint
* Authentication Token
* Integration Schedule
* Account Mapping

---

# Example Mapping

Example of mapping Anzer account code to Odoo:

| Anzer Code | Description | Odoo Account |
| ---------- | ----------- | ------------ |
| 1001       | Cash        | 101000       |
| 2001       | Payables    | 201000       |
| 4001       | Sales       | 401000       |

This ensures all incoming Anzer transactions are correctly posted into Odoo.

---

# Requirements

* Odoo 19
* Python 3.10+
* Docker (optional)
* PostgreSQL

---

# Developer

**Author:**
Aung Min Soe

**Company:**
Glow Together Solutions Co., Ltd

Website
https://gtsolutionsmyanmar.com

---

# Support

For technical support or customization services:

Email
[info@gtsolutionsmyanmar.com](mailto:info@gtsolutionsmyanmar.com)

---

# License

LGPL-3
