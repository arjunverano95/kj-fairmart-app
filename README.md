# 📘 Project Proposal

## KJ Fairmart Supermarket

## Customer Membership System (Digital ID & Customer Engagement Platform)

---

## 1. Executive Summary

KJ Fairmart Supermarket proposes to implement a **Customer Membership System** that provides customers with a **Digital Membership ID (QR-based)** and a platform to view **benefits, promotions, and events** through a **mobile application**. A secure **Admin Portal** will be used by staff to encode membership applications, manage approvals, renew memberships, and publish content.

This project is designed as a **low-cost, fast-launch MVP** focused on digitizing membership identification and customer communication. The system will **not** include points, transactions, POS integration, or vouchers in Phase 1.

---

## 2. Project Objectives

### Primary Objectives

* Digitize KJ Fairmart’s membership card system
* Provide each member with a **Digital ID with QR Code**
* Enable store staff to **facilitate customer sign-ups**
* Enable admin to **approve, reject, and renew memberships**
* Provide customers access to:

  * Benefits
  * Promotions
  * Events and announcements
* Launch quickly within budget

### Constraints (Phase 1 / MVP)

* No points or rewards system
* No voucher system
* No transaction history
* No POS or third-party integrations
* No hardware integrations (scanners, printers, etc.)

---

## 3. Target Members & Membership Structure

### Customer Categories

1. Home Buyers
2. Resellers
3. Institutional / Corporate Accounts (restaurants, offices, etc.)

### Membership Tiers

* Silver
* Gold

### Membership Validity

* Each membership has:

  * Start Date
  * Expiration Date
* Membership is **renewable**
* Renewal is done **by Admin** via Admin Portal

---

## 4. System Components

### A) Admin Portal (Web)

Used by staff and admin to:

* Encode paper-based membership applications
* Approve or reject applications
* Renew memberships
* Manage members
* Manage content (promos, events, benefits, announcements)

### B) Mobile App (Android & iOS)

Used by customers to:

* Log in using their **Card Number**
* View Digital Membership ID (QR)
* View benefits, promotions, and events
* View membership status (Active / Expired)
* View profile

---

## 5. Roles & Permissions

### 5.1 Standard User (Staff / Encoder)

**Can:**

* Encode membership applications (from paper forms)
* Submit applications for approval

**Cannot:**

* Approve or reject applications
* Renew memberships
* Deactivate members
* Manage content (promos/events/benefits/banners)
* Change membership tier or status

---

### 5.2 Admin (Approver / Manager)

**Can:**

* Approve or reject membership applications
* Renew memberships
* Deactivate members
* Manage membership tiers (Silver/Gold)
* Manage content:

  * Benefits
  * Promotions
  * Events
  * Announcements / Notices
  * Banners
* Export member list to Excel

---

## 6. Registration & Credential Flow (Final)

### 6.1 Primary Registration Method (Paper-Based, In-Store)

1. Customer requests membership and fills out a **paper application form**.

2. The form already contains or is assigned a **Card Number**.

3. Staff informs the customer of their **future login credentials**:

   * **Username:** Card Number
   * **Temporary Password:**

     > **LAST NAME (uppercase) + last 3 digits of Card Number**

   Example:

   * Name: Maria **SANTOS**
   * Card No: KJ-2026-0012345
   * Temporary Password: **SANTOS345**

4. Staff collects the form for processing.

5. Staff (Standard User) encodes the application into the system.

6. Admin reviews and **approves or rejects** the application.

7. Upon approval:

   * Membership becomes active
   * Digital ID + QR code is generated
   * Account becomes usable

> ⚠️ Customer may know their credentials in advance, but **login will only work after the account is encoded and approved**.

---

### 6.2 Login Rules

* **Username:** Card Number
* **Password:** Customer password (initially temporary)

If customer attempts to log in before account exists or is approved:

> “Your membership is not yet activated. Please wait for approval or contact the branch.”

---

### 6.3 First Login Security Rule

On first successful login:

* System **forces the customer to change their password**
* Temporary password becomes invalid

---

## 7. Membership Status Lifecycle

Each membership record will have these statuses:

* Paper Submitted (not yet in system)
* Pending Approval (encoded, waiting for admin)
* Active
* Rejected
* Expired
* Deactivated

---

## 8. Membership Expiration & Renewal

* Every membership has an **expiration date**
* When expired:

  * Digital ID will show **EXPIRED**
* Renewal Process (Admin only):

  1. Customer requests renewal at store
  2. Admin finds member record
  3. Admin clicks **Renew Membership**
  4. System extends expiration date (e.g., +1 year)
  5. Status returns to **Active**

---

## 9. Member Data Captured

* Card Number
* Full Name
* Date of Birth
* Address
* Email (optional)
* Customer Category (Home / Reseller / Institution)
* Tier (Silver / Gold)
* Company / Store Name (if applicable)
* Branch Applied At
* ID Type
* ID Photo
* Membership Start Date
* Membership Expiration Date
* Membership Status

---

## 10. Functional Scope

### 10.1 Admin Portal (Web)

**Standard User**

* Encode membership applications
* Upload ID photo
* Submit for approval

**Admin**

* Approval dashboard
* Approve / Reject applications
* Renew memberships
* Deactivate members
* Change tier
* Content management:

  * Benefits
  * Promotions
  * Events
  * Announcements / Notices
  * Banners
* Export members to Excel

---

### 10.2 Mobile App (Android & iOS)

* Login via Card Number
* Forced password change on first login
* Digital ID Card:

  * QR code
  * Name
  * Tier
  * Status (Active / Expired)
* Pages:

  * Benefits
  * Promotions
  * Events
* Profile view (read-only)

---

## 11. Data Storage & Export

* Data stored in system database
* Admin can export membership list to **Excel**

---

## 12. Out of Scope (Phase 1)

* Points & rewards
* Redemption system
* Voucher system
* Transaction history
* POS integration
* Device integration
* Third-party API integrations

---

## 13. Deliverables

* Admin Portal (Web)
* Mobile App (Android)
* Mobile App (iOS)
* Membership database
* Digital ID + QR system
* Content management module
* Excel export
* Basic documentation

---

## 14. Budget & Approach

**Target Budget:** PHP 50,000
**Approach:**

* Build MVP first
* Focus on membership + digital ID + content
* Defer complex features to Phase 2

---

## 15. Success Criteria

### Customers can:

* Log in using Card Number
* Change password on first login
* View Digital ID
* See Active / Expired status
* View benefits, promotions, and events

### Staff/Admin can:

* Encode paper applications
* Approve/reject applications
* Renew memberships
* Manage members
* Publish content
* Export to Excel

---

## 16. Phase 2 (Future Enhancements)

* Voucher system
* Points-based loyalty
* POS integration
* QR scanning validation
* Push notifications / SMS
* Tier-based benefits automation

---

## 17. Items to Confirm

* Membership validity period (e.g., 1 year)
* Renewal duration (e.g., +1 year per renewal)
* Whether expired members can still browse content (recommended: yes)
