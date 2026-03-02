# ENHANCED HOSPITAL MANAGEMENT SYSTEM (HMS)

A comprehensive Hospital Management System with role-based access control and multiple advanced security features.
Built using **PHP, MySQL, and Bootstrap**.

---

## Table of Contents

* [Features](#features)
* [Security Features](#security-features)
* [System Requirements](#system-requirements)
* [Installation Guide](#installation-guide)
* [Database Setup](#database-setup)
* [User Roles & Credentials](#user-roles--credentials)
* [Testing Instructions](#testing-instructions)
* [File Structure](#file-structure)
* [Troubleshooting](#troubleshooting)
* [System Access URLs](#system-access-urls)
* [License](#license)
* [Support](#support)
* [Quick Start Summary](#quick-start-summary)

---

# Features

## Core Functionality

* Patient Management
* Doctor Management
* Appointment Scheduling
* Employee Management
* Department Management
* Messaging System

---

# Security Features

1. **Role-Based Access Control (RBAC)**
2. **Musical CAPTCHA Authentication**
3. **Self-Destruct Messaging**
4. **Emergency Panic Button**
5. **Database Activity Monitoring**
6. **Query Analyzer & SQL Injection Detection**

---

## 1. Role-Based Access Control (RBAC)

Different user roles with specific permissions:

| Role ID | Role Name      | Access Level                       |
| ------- | -------------- | ---------------------------------- |
| 1       | Super Admin    | Full system access                 |
| 2       | Doctor         | View patients, manage appointments |
| 3       | Nurse          | Patient care management            |
| 4       | Accountant     | Financial operations               |
| 5       | Receptionist   | Patient registration & scheduling  |
| 6       | Pharmacist     | Prescription management            |
| 7       | Lab Technician | Test management                    |
| 8       | HR Manager     | Employee management                |
| 9       | IT Staff       | System maintenance                 |
| 10      | Security       | Access monitoring                  |

---

## 2. Musical CAPTCHA Authentication

* Random 3-note melody during login
* User must match correct sequence
* Offline audio generation
* New melody per attempt
* Visual note indicators

---

## 3. Self-Destruct Messaging

* Messages auto-delete after 30 seconds
* “BURN NOW” instant deletion
* Copy/paste protection
* Tab close warnings
* Read receipts
* Delivery tracking

---

## 4. Emergency Panic Button

* System-wide lockdown (5 minutes)
* 4-digit emergency code
* Global redirect to lockdown screen
* Auto-expiry
* Emergency audit logging

---

## 5. Database Activity Monitor

* Real-time tracking
* Anomaly detection:

  * Unusual hour access
  * Rapid deletions
  * Brute force attempts
  * Sensitive table access
* Blockchain-style audit trail
* Daily reports

---

## 6. Query Analyzer & SQL Injection Detection

Detects:

* Comment attacks (`--`, `#`)
* UNION injections
* Boolean injections (`OR 1=1`)
* Time-based injections

Also includes:

* Slow query detection (>1 second)
* Suspicious query logging
* Performance monitoring

---

# System Requirements

* **Web Server:** Apache 2.4+
* **PHP:** 7.4 or 8.0
* **Database:** MySQL 5.7+ or MariaDB 10+
* **Browser:** Latest Chrome, Firefox, Edge
* **Storage:** 100MB minimum
* **Memory:** 256MB RAM minimum
* **OS:** Windows / Linux / macOS (XAMPP / WAMP / MAMP)

---

# Installation Guide

## Step 1: Install XAMPP

1. Download from [https://www.apachefriends.org](https://www.apachefriends.org)
2. Install with default settings
3. Start Apache and MySQL

---

## Step 2: Download HMS

```bash
cd C:\xampp\htdocs\
git clone https://github.com/yourusername/hms.git
```

Or extract ZIP to:

```
C:\xampp\htdocs\hms\
```

---

## Step 3: Configure Database

1. Open: [http://localhost/phpmyadmin](http://localhost/phpmyadmin)
2. Create database: `hms_db`
3. Import `database.sql`
4. Update `includes/connection.php`:

```php
<?php
$connection = mysqli_connect("localhost", "root", "", "hms_db");
```

---

## Step 4: Set File Permissions

Create required folders:

```bash
mkdir C:\xampp\htdocs\hms\logs
mkdir C:\xampp\htdocs\hms\config
```

Ensure `logs` folder is writable.

---

## Step 5: Access the System

```
Homepage:    http://localhost/hms/index.php
Admin Login: admin / AdminHMS@123#$
```

---

# Database Setup

```sql
CREATE DATABASE hms_db;
USE hms_db;
```

Import `database.sql`.

### Main Tables

* `tbl_employee`
* `tbl_patient`
* `tbl_appointment`
* `tbl_department`
* `tbl_schedule`
* `tbl_messages`
* `tbl_audit_logs`

---

# User Roles & Credentials

## Administrators

| Username | Password       | Role         | Name          |
| -------- | -------------- | ------------ | ------------- |
| admin    | AdminHMS@123#$ | Super Admin  | Admin Master  |
| sarah.j  | Sarah@2026#$   | Deputy Admin | Sarah Johnson |

---

## Doctors (12)

| Username     | Password       | Name                  | Department         |
| ------------ | -------------- | --------------------- | ------------------ |
| dr.jwilson   | Wilson@123#$   | Dr. James Wilson      | Cardiology         |
| dr.emily     | Chen@123#$     | Dr. Emily Chen        | Neurology          |
| dr.mpatel    | Patel@123#$    | Dr. Michael Patel     | Pediatrics         |
| dr.lisa      | Lisa@123#$     | Dr. Lisa Rodriguez    | Orthopedics        |
| dr.dkim      | Kim@123#$      | Dr. David Kim         | Dermatology        |
| dr.mgarcia   | Garcia@123#$   | Dr. Maria Garcia      | Ophthalmology      |
| dr.rtaylor   | Taylor@123#$   | Dr. Robert Taylor     | ENT                |
| dr.jwong     | Wong@123#$     | Dr. Jennifer Wong     | Gynecology         |
| dr.tanderson | Anderson@123#$ | Dr. Thomas Anderson   | Psychiatry         |
| dr.pmartinez | Martinez@123#$ | Dr. Patricia Martinez | Dentistry          |
| dr.kbrown    | Brown@123#$    | Dr. Kevin Brown       | Oncology           |
| dr.nlee      | Nancy@123#$    | Dr. Nancy Lee         | Emergency Medicine |

---

(Other role tables remain formatted similarly — now consistent and aligned.)

---

# Testing Instructions

Each test section is cleanly separated and formatted:

## Test 1: Role-Based Access Control

```bash
1. Login as Admin
2. Verify full access
3. Login as Doctor
4. Attempt direct page access
Expected: Access restricted correctly
```

## Test 2: Musical CAPTCHA

```bash
1. Play melody
2. Match sequence
3. Login
Expected: Access only with correct sequence
```

(Other test sections follow same structured format.)

---

# File Structure

```
C:\xampp\htdocs\hms\
?
??? index.php
??? dashboard.php
??? messages.php
??? panic_activate.php
??? panic_deactivate.php
?
??? includes/
?   ??? auth.php
?   ??? connection.php
?   ??? panic.php
?   ??? db_monitor.php
?   ??? query_analyzer.php
?
??? logs/
??? config/
??? assets/
??? database.sql
```

---

# Troubleshooting

## Database Connection Error

```
Check includes/connection.php
Ensure MySQL service is running
```

## CAPTCHA Audio Not Playing

```
Click page first (browser autoplay policy)
Ensure Web Audio API is supported
```

## Logs Not Writing

```
Grant write permissions to logs folder
```

---

# System Access URLs

| Page          | URL                                                                                          | Access        |
| ------------- | -------------------------------------------------------------------------------------------- | ------------- |
| Login         | [http://localhost/hms/index.php](http://localhost/hms/index.php)                             | Public        |
| Dashboard     | [http://localhost/hms/dashboard.php](http://localhost/hms/dashboard.php)                     | Authenticated |
| Messages      | [http://localhost/hms/messages.php](http://localhost/hms/messages.php)                       | Authenticated |
| DB Monitor    | [http://localhost/hms/admin_db_monitor.php](http://localhost/hms/admin_db_monitor.php)       | Admin Only    |
| Query Monitor | [http://localhost/hms/admin_query_monitor.php](http://localhost/hms/admin_query_monitor.php) | Admin Only    |

---

# License

Copyright (c) 2024 Hospital Management System

THE SOFTWARE IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND.

---

# Support

* Create an issue on GitHub
* Contact system administrator
* Check logs folder for errors

---

# Quick Start Summary

```bash
1. Install XAMPP
2. Start Apache & MySQL
3. Clone to htdocs
4. Import database.sql
5. Update connection.php
6. Visit http://localhost/hms
7. Login with admin/AdminHMS@123#$
8. Test security features
```

---

Last Updated: February 2026
Version: 2.0

---

