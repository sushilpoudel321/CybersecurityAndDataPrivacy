
# Booking System – Phase 2 Test Report

## 1. Overview
- **Application tested:** Booking System Phase 2
- **URL:** http://localhost:8002
- **Testing date:** [Add your date]
- **Testers:** Roshani Pathak & Sushil

The purpose of this report was to evaluate the functionality and security of the Phase 2 version of the Booking System application. Testing included input validation checks, penetration attempts, and general user interface behavior.

---

## 2. Tests Performed

### 2.1 Email Field Tests (SQL Injection Attempt)
I attempted several SQL injection payloads such as:

```
' OR 1=1--
test@example.com' OR 1=1--
```

**Result:**  
The application displayed an error message:  
“A part following '@' should not contain the symbol '”.  
This indicates that the front-end validation blocks SQL injection characters.  
**Outcome:** Secure behavior at client side; backend not tested directly.

---

### 2.2 Password Field Tests
Tested weak passwords:
- `123` → rejected (too short)
- `12345` → accepted

**Findings:**
- Minimum length of 5 characters is enforced.
- No requirements for complexity (uppercase, symbols, numbers).

**Risk:** Weak passwords can still be used, making accounts easier to compromise.

---

### 2.3 Birthdate Field Tests
Tested inputs:
- Yesterday's date → accepted  
- Future dates → rejected (“Birthdate cannot be in the future.”)
- Very old dates (e.g., 1908) → accepted

**Findings:**  
Age validation is weak. Unrealistic ages are allowed.  
Only future dates are blocked.

---

### 2.4 Role Selection Tests (Critical Access Control Issue)
During registration, the "Role" dropdown allowed selecting:
- **Reserver**
- **Administrator**

Both roles successfully completed registration.

**Critical vulnerability:**  
Any user can assign themselves as an Administrator.  
This is a privilege escalation risk and a major security issue.

---

## 3. Summary of Findings

| Category | Finding | Risk Level |
|---------|---------|------------|
| Email Validation | SQL injection blocked by client-side validation | Low/Positive |
| Password Policy | Weak enforcement (only length) | Medium |
| Birthdate Input | Unrealistic ages allowed | Medium |
| Role Assignment | Users can register as Administrator | **High / Critical** |

---

## 4. Conclusion
Phase 2 of the Booking System includes improved input validation (especially for email and future dates), but still contains significant security risks.  
The most serious issue is unrestricted role assignment, allowing any user to create an Administrator account. This vulnerability must be addressed immediately.

Additional improvements should include stronger password policies and proper age validation.

---
