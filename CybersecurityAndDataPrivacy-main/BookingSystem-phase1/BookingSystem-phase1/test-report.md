TEST REPORT – BOOKING SYSTEM PHASE 1

Introduction

Testers:Testers: Roshani Pathak and Sushil Poudel.

Purpose:
The purpose of this test was to examine how the registration page works, find any problems or strange behaviour, and check for basic security weaknesses. Since this is Phase 1, only the registration part was tested.

Scope:
Tested components: the registration form, including email, password, and age fields, and how the system responds to different inputs. I also used OWASP ZAP to run an automated scan.
Exclusions: I did not test login, booking features, admin pages, backend code, or denial-of-service attacks.
Test approach: Gray-box testing.

Test environment and dates:
Start: 28.11.2025
End: 28.11.2025
Environment details: Windows 11, Docker Desktop running the web container and PostgreSQL database, Opera browser, and OWASP ZAP version 2.16.1.

Assumptions and constraints:
There was limited time for the assignment. Only the registration feature is available in this phase. I assumed the registration would at least work with valid inputs, but every attempt failed. I had no access to backend code, only the running application.

Executive Summary

Short summary:
During testing, the registration page failed every time with the same message: “Error during registration.” This happened with both valid and invalid inputs. This made it difficult to understand what was wrong. The ZAP scan also found several missing security headers.

Overall risk level: Medium

Top 5 immediate actions:

Fix the backend issue that is blocking all registrations.

Add proper error messages so users know which field has the problem.

Add missing security headers for basic protection.

Make the age requirement visible on the registration page.

Improve the validation for email and password.

Severity scale and definitions

High: A serious problem that can cause big security issues or data breaches. Needs to be fixed immediately.
Medium: An issue that can be used or might cause problems in some situations. Should be fixed soon.
Low: A small issue or weakness. Fix when possible.
Info: Not harmful but good to fix for better security.

Findings

Finding F01 – Medium severity
The system showed “Error during registration” for all test inputs. This made it impossible to understand what caused the error and made testing difficult.

Finding F02 – Low severity
If I entered an email without the “@” symbol, registration failed. However, the system did not explain this and only showed the same error message.

Finding F03 – Low severity
The age requirement seems to work because entering age 10 also failed, but the system does not show the rule anywhere. Users have no idea why the age is wrong.

Finding F04 – Low severity
Weak passwords like “123” or “aaa” also failed, but again there was no explanation. It is unclear what the password rules are.

Finding F05 – Info
OWASP ZAP reported missing security headers such as Content-Security-Policy, X-Frame-Options, and X-Content-Type-Options. These headers are commonly used to improve security on websites.

OWASP ZAP Test Report 

Purpose:
The automated ZAP scan was used to identify technical weaknesses. The scan mainly found missing security headers and a few informational issues. The full ZAP report is attached separately as “zap-report.html” in the BookingSystem-Phase1 folder.

End of report.
