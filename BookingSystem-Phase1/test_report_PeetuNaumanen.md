# 1️⃣ Introduction

**Tester(s):**  
- Name:  Peetu Naumanen

**Purpose:**  
- Finding vulnerabilities in the BookingSystem web application


**Time & dates:**  
- Start:  2/2/2026 9:00 AM
- End:  2/2/2026 10:00 AM



---

# 2️⃣ Executive Summary

**Overall risk level:** (Low / Medium / High / Critical)

**Top 5 immediate actions:**  
1.  Fix SQL injection vulnerabilities
2.  Eliminate path travelsal risks
3.  Add missing security headers
4.  Supperss error disclosure
5.  Implement CSRF protection
   

---

# 3️⃣ Severity scale & definitions

|  **Severity Level**  | **Description**                                                                                                              | **Recommended Action**           |
| -------------------- | ---------------------------------------------------------------------------------------------------------------------------- | -------------------------------- |
|      🔴 **High**     | A serious vulnerability that can lead to full system compromise or data breach (e.g., SQL Injection, Remote Code Execution). | *Immediate fix required*         |
|     🟠 **Medium**    | A significant issue that may require specific conditions or user interaction (e.g., XSS, CSRF).                              | *Fix ASAP*                       |
|      🟡 **Low**      | A minor issue or configuration weakness (e.g., server version disclosure).                                                   | *Fix soon*                       |
| 🔵 **Info** | No direct risk, but useful for system hardening (e.g., missing security headers).                                            | *Monitor and fix in maintenance* |


---

# 4️⃣ Findings 


1. Missing Anti-clickjacking Header - The response does not protect against 'ClickJacking' attacks.
2. Application Error Disclosure - This page contains an error/warning message that may disclose sensitive information like the location of the file that produced the unhandled exception. This information can be used to launch further attacks against the web application.
3. X-Content-Type-Options Header Missing - The Anti-MIME-Sniffing header X-Content-Type-Options was not set to 'nosniff'. This allows older versions of Internet Explorer and Chrome to perform MIME-sniffing on the response body, potentially causing the response body to be interpreted and displayed as a content type other than the declared content type.
4. User Agent Fuzzer - Check for differences in response based on fuzzed User Agent (eg. mobile sites, access as a Search Engine Crawler). Compares the response statuscode and the hashcode of the response body with the original response.
5. SQL Injection - Do not trust client side input, even if there is client side validation in place.

---

