# Authorization Test Report – Phase 3

This document describes authorization testing performed on the Booking System
(Phase 3). The goal was to verify what each role (Guest, Reserver, Administrator)
can and cannot do, and to identify any authorization issues in the implementation.

Testing was conducted using:
- Manual browser testing
- OWASP ZAP scanning

Target application:
http://localhost:8003

---

## 🧑‍🦲 Guest (Not Logged In)

### ✅ Can do
- Can view the landing page — `/`
- Can view booked resources without seeing reserver identities — `/`
- Can access login page — `/login`
- Can access registration page — `/register`

### ❌ Cannot do
- Cannot add a new resource — button disabled
- Cannot add a new reservation — button disabled
- Cannot access reservation creation page — `/reservation`
- Cannot access profile page — `/profile`
- Cannot access admin pages — `/admin`

✔ Guest behavior matches the specifications.

---

## 🧑‍💼 Reserver (Logged In User)

### ✅ Can do
- Can log in and log out — `/login`, `/logout`
- Can view the landing page after login — `/`
- Can create a new reservation — “Add a new reservation” button works
- Can view booked resources — `/`
- ⚠️ Can add a new resource — “Add a new resource” button works (unexpected)

### ❌ Cannot do
- Cannot access admin dashboard — `/admin`
- Cannot access admin users page — `/admin/users`
- Cannot delete users — `/api/admin/users/:id`

### ⚠️ Authorization Issues
- A Reserver can add new resources, even though resource management should be
  restricted to the Administrator role according to the specifications.
- This indicates missing or insufficient backend authorization enforcement.

---

## 🧑‍💼🛡️ Administrator

### ✅ Can do
- Can access admin dashboard — `/admin`
- Can add, modify, and delete resources — `/admin/resources`
- Can manage all reservations — `/admin/reservations`
- Can view and delete users — `/admin/users`

### ❌ Cannot do
- No unnecessary or restricted actions observed beyond the administrator role.

✔ Administrator behavior matches the specifications.

---

## 🔍 Summary

Authorization controls are partially enforced.
Guest access is correctly restricted.
A critical authorization issue was identified where the Reserver role can perform
administrator-only actions such as adding new resources.
Administrator functionality behaves as expected.
