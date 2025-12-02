
# ZAP Report – Round 2 (Phase 1, Part 2)

## 1. General Information
- **Application:** Booking System – Phase 1 – Part 2 (Updated Version)
- **Tester:** Roshani Pathak,Sushil Poudel 
- **Date:** 02.12.2025  
- **Tool Used:** OWASP ZAP 2.16.1  
- **Testing Type:** Automated security scan  
- **Environment:**  
  - Windows 11  
  - Docker Desktop running application and PostgreSQL  
  - Opera browser  

## 2. Scope of the Scan
The purpose of this second ZAP scan was to check whether any issues found in Round 1 were fixed after the updated application version was released.

**Pages Included:**
- `/register`
- Any other resources ZAP discovered automatically

**Exclusions:**
- Login, booking, admin sections (not available in Phase 1)

## 3. Summary of Results (Round 2)
Based on the scan results collected during Round 2:

- **High severity alerts:** 0  
- **Medium severity alerts:** 0  
- **Low severity alerts:** 0  
- **Informational alerts:** A few, mostly related to missing headers  

### Overall change compared to Round 1:
- Missing headers such as **Content-Security-Policy**, **X-Frame-Options**, and **X-Content-Type-Options** are **still present**.  
- No new serious issues were introduced.  
- The security posture remains roughly **the same as Round 1**.

## 4. Detailed Findings (Round 2)

### Finding ZR2-01 – Missing Security Headers  
- **Severity:** Info  
- **Status vs Round 1:** Not Fixed  
- **Description:**  
  ZAP reports the same missing headers as before:
  - Content-Security-Policy  
  - X-Frame-Options  
  - X-Content-Type-Options  
  These help protect against clickjacking, MIME sniffing, and cross-site scripting.

- **Why it matters:**  
  Without these headers, the application remains more vulnerable to browser-based attacks.

- **Recommendation:**  
  Add these headers at server level or through the web framework configuration.

---

### Finding ZR2-02 – Other Informational Alerts  
- **Severity:** Info  
- **Status vs Round 1:** Unchanged  
- **Description:**  
  Minor informational alerts such as missing caching headers and cookie settings.

- **Recommendation:**  
  Improve header configuration when backend development progresses.

---

## 5. Comparison to Round 1
- No high or medium severity issues were detected in either Round 1 or Round 2.  
- The missing headers from Round 1 remain unfixed.  
- No new vulnerabilities were introduced.  
- The application’s risk level remains **Medium**, mainly due to lack of clarity in error handling and missing security headers (noted in manual testing and in the Round 1 test report).

## 6. Conclusion
The updated version of the application does not show significant improvement in security based on ZAP testing. The same informational issues appear again, particularly missing security headers. These should be addressed when server-side development continues.

End
