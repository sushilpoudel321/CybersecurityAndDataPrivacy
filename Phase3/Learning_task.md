# Authorization Testing Assignment – Phase 3

## 🎯 Goal of the Assignment
The goal of this assignment is to evaluate authorization controls in the Booking
System application by testing what different user roles can and cannot do.

The roles tested are:
- Guest (not logged in)
- Reserver (logged in user)
- Administrator

The focus is on verifying that authorization decisions are correctly enforced
at the backend and that no unauthorized access is possible.

---

## 🧩 Background
The Booking System is accessed via a web browser and provides the following
functionality according to the specifications:

- Users can register and log in
- A logged-in user acts as either a Reserver or an Administrator
- Administrators can add, remove, and modify resources and reservations
- Administrators can delete Reserver accounts
- Reservers can book resources if they are over 15 years old
- Resources can be booked on an hourly basis
- Booked resources are visible without login, but reserver identities are hidden
- The system should comply with GDPR and Privacy by Design principles

---

## 🧭 Assignment Tasks
The following testing activities are required:

1. Browser-based testing for each role:
   - Guest
   - Reserver
   - Administrator

2. Verification of:
   - Accessible pages and actions
   - Blocked pages and actions
   - Unexpected or unauthorized behavior

3. Tool-assisted testing using OWASP ZAP to:
   - Discover hidden pages and endpoints
   - Identify authorization-related issues
   - Validate backend access control

---

## 🧪 Testing Methods
The following methods are used in this assignment:

- Manual browser testing
- OWASP ZAP active and passive scanning

---

## 🧾 Deliverables
The following files must be provided in the GitHub repository:

1. **Authorization Test Report**
   - File name: `auth_test_report.md`
   - Contains role-based testing results and findings

2. **ZAP Scan Report**
   - File name: `zap_report_round4.md` (or HTML equivalent if Markdown export is unavailable)
   - Contains automated scan results from OWASP ZAP

---

## ✔️ Completion Criteria
The assignment is considered complete when:
- Phase 3 containers run successfully
- Authorization testing is documented
- OWASP ZAP scan has been performed
- All required files are present in the repository
