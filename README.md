# Project Proposal and Scope of Work

## KJ Fairmart Supermarket

## Customer Membership System (Digital ID & Customer Engagement Platform)

---

## 1. Executive Summary

KJ Fairmart Supermarket intends to implement a Customer Membership System that provides members with a QR-based Digital Membership ID and a customer-facing mobile application for viewing announcements, promotions, benefits, and events. The solution includes an Admin Portal to support store operations for membership application encoding, administrative approval, membership renewals, member management, and content publishing.

This proposal outlines a streamlined, cost-effective MVP designed for quick deployment while establishing a solid foundation for future enhancements. Phase 1 will intentionally exclude points, vouchers, transaction tracking, POS integrations, and hardware integrations to keep the project within budget and enable rapid launch.

---

## 2. Project Objectives

### 2.1 Primary Objectives

* Digitize the KJ Fairmart membership card program with a unified, secure member database.
* Provide members a Digital ID with QR code for in-store validation and future expansion.
* Enable branch staff to facilitate customer sign-ups through an assisted, paper-based intake process.
* Provide administrative workflows for application approval/rejection, renewals, and membership status management.
* Provide a content publishing platform for customer communications (announcements, promotions, benefits, events, banners).
* Deliver mobile applications (Android and iOS) for member access to ID and engagement content.
* Provide administrative Settings for managing system users and branches.

### 2.2 Phase 1 Constraints

* No points or rewards computation.
* No redemption or voucher system.
* No transaction history or purchase tracking.
* No POS integration or third-party API integrations.
* No device/hardware integration (e.g., barcode scanners, printers, magstripe readers).

---

## 3. Membership Model and Branch Coverage

### 3.1 Membership Coverage

Membership accounts are company-wide and usable across all KJ Fairmart branches. Each member has a single membership record and a single card number recognized at any branch.

### 3.2 Branch as Metadata

Branch information is captured for operational tracking and reporting purposes only. Examples include:

* Branch Applied At
* Branch filter and reporting in Admin Portal
* Optional renewal processing branch (if required later)

Membership ownership is not limited to a branch to prevent cross-branch recognition issues and to support future expansions such as voucher or points-based programs.

---

## 4. Target Members and Membership Structure

### 4.1 Member Categories

* Home Buyers
* Resellers
* Institutional / Corporate Accounts (restaurants, offices, etc.)

### 4.2 Membership Tiers

* Silver
* Gold

### 4.3 Validity and Renewal

* Membership records include Start Date and Expiration Date.
* Membership can expire and is renewable.
* Membership renewal is performed by an Admin user through the Admin Portal.

---

## 5. Solution Components

### 5.1 Admin Portal (Web)

A web-based portal used for membership operations and content management.

Core responsibilities:

* Encode paper-based membership applications.
* Process approvals/rejections (Admin).
* Manage renewals (Admin).
* Maintain member records and statuses.
* Publish engagement content (Admin).
* Manage system users and branches (Admin).

**Admin Portal Navigation (Sidebar Modules):**

* Dashboard
* Member Registration
* Cardholder Management
* Content Management
* Settings (Users + Branches)
* Log Out

### 5.2 Mobile Application (Android & iOS)

A customer-facing mobile app for membership access and engagement.

**Bottom Navigation Tabs:**

* Home
* Benefits
* Digital ID
* Profile

---

## 6. User Roles and Access Control

### 6.1 Standard User (Staff / Encoder)

Purpose: Facilitate membership registration intake and encoding.

**Permitted Actions**

* Encode membership applications from paper forms.
* Upload member ID photo during application encoding (if applicable).
* Submit encoded applications for Admin review.

**Restricted Actions**

* Cannot approve or reject applications.
* Cannot renew memberships.
* Cannot deactivate memberships.
* Cannot change tier or membership status.
* Cannot manage content.
* Cannot manage system settings (users/branches).

### 6.2 Admin (Approver / Manager)

Purpose: Manage approvals, membership lifecycle, content publishing, and system settings.

**Permitted Actions**

* Approve or reject membership applications.
* Renew memberships and extend expiration dates.
* Deactivate memberships.
* Manage tier assignment (Silver/Gold).
* Publish and manage content:

  * Announcements / Notices
  * Promotions
  * Benefits
  * Events
  * Banners
* Export member lists to Excel.
* Manage Settings:

  * User Management (create/edit/deactivate staff/admin users)
  * Branch Management (create/edit branches)

---

## 7. Registration, Approval, and Credential Workflow

### 7.1 Primary Registration Method (Paper-Based, In-Store)

1. Customer completes a paper membership application form at the branch.
2. The form contains or is assigned a Card Number.
3. Staff provides the customer with their future login credentials:

   * **Username:** Card Number
   * **Temporary Password:** LAST NAME (uppercase) + last 3 digits of Card Number

     * Example: Name: Maria SANTOS, Card No: KJ-2026-0012345 → Temp Password: SANTOS345
4. Staff retains the form for encoding.
5. Staff (Standard User) encodes the application into the Admin Portal.
6. The application is recorded as Pending Approval.
7. Admin approves or rejects the application.
8. Upon approval:

   * Membership becomes Active.
   * Digital ID with QR code becomes available in the mobile app.
   * Customer account login becomes available.

> Customers may know their credentials in advance; however, login becomes available only after the application is encoded and approved.

### 7.2 Login Rules

* **Username:** Card Number
* **Password:** Temporary password until changed by the customer.

If a customer attempts to log in before their account is available or approved, the app should display:

* “Your membership is not yet activated. Please wait for approval or contact the branch.”

### 7.3 First Login Security Requirement

On the customer’s first successful login:

* The app must require a password change.
* The temporary password is no longer valid after a successful change.

---

## 8. Membership Status Lifecycle

The system supports clear membership states:

* Paper Submitted (not yet encoded in system)
* Pending Approval
* Active
* Rejected
* Expired
* Deactivated

---

## 9. Membership Expiration and Renewal

* Membership includes an Expiration Date.
* When expired, the Digital ID must show a clearly visible “Expired” status.
* Renewal is performed by Admin users only:

  1. Customer requests renewal.
  2. Admin locates the member record.
  3. Admin triggers “Renew Membership.”
  4. The system extends Expiration Date based on configured rules.
  5. Status returns to Active.

---

## 10. Member Data Captured

The system will store the following information per member:

* Card Number (unique)
* Full Name
* Date of Birth
* Address
* Email (optional)
* Category (Home / Reseller / Institution)
* Tier (Silver / Gold)
* Company / Store Name (if applicable)
* Branch Applied At (metadata)
* ID Type
* ID Photo
* Membership Start Date
* Membership Expiration Date
* Membership Status

---

## 11. Functional Scope

### 11.1 Admin Portal

**A) Member Registration (Standard User)**

* Encode new membership applications.
* Capture required member details and attach ID photo.
* Submit application for approval.

**B) Cardholder Management (Admin)**

* Search and filter members.
* View member details.
* Approve or reject applications.
* Renew membership.
* Deactivate membership.
* Export members to Excel.

**C) Content Management (Admin)**

* Create/edit/publish:

  * Announcements / Notices
  * Promotions
  * Benefits
  * Events
  * Banners

**D) Dashboard (Admin)**

* High-level indicators such as:

  * Total members
  * Pending approvals
  * Members expiring soon (recommended)

**E) Settings (Admin)**

* User Management:

  * Create/edit/deactivate system users (staff/admin).
* Branch Management:

  * Create/edit branch records used for application capture and filtering.

### 11.2 Mobile Application

**A) Authentication**

* Login using Card Number + Password.
* First-login password change flow.

**B) Home Tab**

* Display announcements, promotions, and events in a clean banner/feed layout.

**C) Benefits Tab**

* Display membership benefits and privileges, including tier-related information (Silver/Gold).

**D) Digital ID Tab**

* Display QR-based digital membership card including:

  * Card number
  * Member name
  * Tier
  * Membership status (Active/Expired)

**E) Profile Tab**

* View and update profile information (fields to be confirmed if editable).
* Change password.
* Log out.

---

## 12. Data Storage and Export

* Member and content data will be stored in a database suitable for production use.
* Admin users will have the ability to export member lists to Excel. Export should support current filters when applicable.

---

## 13. Out of Scope (Phase 1)

The following items are excluded from Phase 1 and may be considered for a future phase:

* Points/rewards computation
* Redemption flows
* Voucher issuance and consumption
* Transaction history and purchase tracking
* POS integrations
* Hardware/device integrations
* Third-party API integrations
* Push notifications/SMS campaigns (optional future enhancement)

---

## 14. Deliverables

* Admin Portal (Web)
* Mobile App (Android)
* Mobile App (iOS)
* Member database and core membership workflows
* Digital ID + QR generation and display
* Content management module (Admin Portal)
* Excel export functionality
* Basic documentation (admin guide and operational flow)

---

## 15. Budget and Delivery Approach

**Target Budget:** PHP 50,000

Delivery will prioritize an MVP build approach:

* Implement core membership and content workflows first.
* Provide a stable production baseline.
* Defer advanced loyalty mechanics and integrations to later phases.

---

## 16. Success Criteria

### Customer Success Criteria

* Customers can log in using card number once approved.
* Customers are prompted to change password on first login.
* Customers can view a Digital ID with QR code and see membership status clearly.
* Customers can access Home (announcements/promos/events), Benefits, and Profile screens.

### Administrative Success Criteria

* Standard users can encode membership applications and submit for approval.
* Admin can approve/reject applications, renew memberships, deactivate accounts, and manage tiers.
* Admin can publish and manage customer-facing content.
* Admin can export members to Excel.
* Admin can manage system users and branches via Settings.

---

## 17. Items for Confirmation

To complete implementation details, the following items should be confirmed:

* Membership validity period (e.g., 12 months)
* Renewal extension rule (e.g., extend by 12 months per renewal)
* Which profile fields are editable by customers in the mobile app
* Whether expired members can still browse content (recommended: yes)

---
