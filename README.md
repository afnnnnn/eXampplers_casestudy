# eXampplers_casestudy

Group eXampplers
- Afnan Iman bin Azman (1920311)
- Sharul Irfan bin Sharul Isram (1921825)
- Muhammad Hazim bin Ibrahim (2014309)

Case Study website: https://ibayaq.kedah.gov.my/

-Description-

--------------------------------------------------------------------------------------------------------------------------------------------------------------------

**Automated scan:**
4 orange flags, 4 yellow flags, 5 blue flags

**Manual scan:** 
8 orange flags, 7 yellow flags, 5 blue flags

-------------------------------------------------------------------------------------------------------------------------------------------------------------------
# Server OS and Server-Side Scripting used (Windows or Linux, PHP or ASP.net or JavaScript, etc

## Automated Scan and manual scan

**Alert: Cross-Domain JavaScript Source File Inclusion**
- **Identify**
  - Risk: Low
  - Confidence: Medium
  - CWE ID: 829

 - **Evaluate**
   - The page includes one or more script files from a third-party domain
  
  - **Prevent**
    - Ensure JavaScript source files are loaded from only trusted sources, and the sources can't 
be controlled by end users of the application.

**Alert: Timestam disclosure - Unix**
- **Identify**
  - Risk: Low
  - Confidence: low
  - CWE ID: 200

 - **Evaluate**
   - A timestamp was disclosed by the application/web server - Unix
  
  - **Prevent**
    - Manually confirm that the timestamp data is not sensitive, and that the data cannot be aggregated to disclose exploitable patterns.

## Manual Scan only

**Alert: Server Leaks Version Information via "Server" HTTP Response Header Field**
- **Identify**
  - URL: [https://www.google-analytics.com/g/](https://www.google-analytics.com/g/collect?v=2&tid=G-WB0WT1G0JH&gtm=45je4580v890436127za200&_p=1715503489872&gcd=13l3l3l3l1&npa=0&dma=0&cid=1025691879.1715503492&ul=en-us&sr=1536x864&uaa=x86&uab=64&uafvl=Chromium%3B124.0.6367.158%7CGoogle%2520Chrome%3B124.0.6367.158%7CNot-A.Brand%3B99.0.0.0&uamb=0&uam=&uap=Windows&uapv=15.0.0&uaw=0&frm=0&pscdl=noapi&_s=1&sid=1715503491&sct=1&seg=0&dl=https%3A%2F%2Fibayaq.kedah.gov.my%2F&dt=iBayaq&en=page_view&_fv=1&_nsi=1&_ss=1&_ee=1&tfd=3805)
  - Risk: Low
  - Confidence: High
  - CWE ID: 200 (Information Exposure)

 - **Evaluate**
   - The web/application server is leaking version information via the "Server" HTTP response header. Access to such information may facilitate attackers identifying other vulnerabilities your web/application server is subject to.
  
  - **Prevent**
    - Ensure that your web server, application server, load balancer, etc. is configured to suppress the "Server" header or provide generic details.

-------------------------------------------------------------------------------------------------------------------------------------------------------------------
# CSP

## Automated Scan and Manual Scan
**Alert: CSP: Wildcard Directive**
- **Identify**
  - Risk: medium
  - Confidence: medium
  - CWE ID: 693

 - **Evaluate**
   - Content Security Policy (CSP) is an added layer of security that helps to detect and mitigate 
     certain types of attacks. Including (but not limited to) Cross Site Scripting (XSS), and data
     injection attacks. These attacks are used for everything from data theft to site defacement
     or distribution of malware. CSP provides a set of standard HTTP headers that allow website
     owners to declare approved sources of content that browsers should be allowed to load on
     that page — covered types are JavaScript, CSS, HTML frames, fonts, images and
     embeddable objects such as Java applets, ActiveX, audio and video files.
  
  - **Prevent**
    - Ensure that your web server, application server, load balancer, etc. is properly configured to
      set the Content-Security-Policy header.


  **Alert: CSP: script-src unsafe-eval**
- **Identify**
  - Risk: medium
  - Confidence: medium
  - CWE ID: 693

 - **Evaluate**
   - that scripts can be executed with the ability to use eval() and similar dynamic code execution functions.
  
  - **Prevent**
    - Ensure that your web server, application server, load balancer, etc. is properly configured to set the Content-Security-Policy header.
   
    **Alert: CSP: script-src unsafe-inline**
- **Identify**
  - Risk: medium
  - Confidence: medium
  - CWE ID: 693

 - **Evaluate**
   - The unsafe-inline value in the script-src directive of a Content Security Policy (CSP) indicates that inline JavaScript code (code directly embedded within HTML) is allowed to be executed.
  
  - **Prevent**
    - Ensure that your web server, application server, load balancer, etc. is properly configured to set the Content-Security-Policy header
   
    **Alert: CSP: style-src unsafe-inline**
- **Identify**
  - Risk: medium
  - Confidence: medium
  - CWE ID: 693

 - **Evaluate**
   - The unsafe-inline value in the style-src directive of a Content Security Policy (CSP) indicates that inline CSS styles (styles directly embedded within HTML) are allowed to be applied.
  
  - **Prevent**
    - Ensure that your web server, application server, load balancer, etc. is properly configured to set the Content-Security-Policy header.

-------------------------------------------------------------------------------------------------------------------------------------------------------------------
# HTTPS Implementation (TLS/SSL)

## Automatic Scan


## Manual Scan only

**Alert: Strict-Transport-Security Header Not Set**
- **Identify**
  - URL: [https://s.go-mpulse.net/boomerang/](https://s.go-mpulse.net/boomerang/PGSPU-YYQDA-PWA6K-GNMUD-FJWFB)
  - Risk: Low
  - Confidence: High
  - CWE ID: 319

 - **Evaluate**
   - HTTP Strict Transport Security (HSTS) is a web security policy mechanism whereby a web server declares that complying user agents (such as a web browser) are to interact with it using only secure HTTPS connections (i.e. HTTP layered over TLS/SSL). HSTS is an IETF standards track protocol and is specified in RFC 6797.
  
  - **Prevent**
    - Ensure that your web server, application server, load balancer, etc. is configured to enforce Strict-Transport-Security.

-------------------------------------------------------------------------------------------------------------------------------------------------------------------
# Potential XXS

## Automatic Scan and Manual Scan

**Alert: Cookie No HttpOnly Flag**
- **Identify**
  - URL: [https://ibayaq.kedah.gov.my/](https://ibayaq.kedah.gov.my/)
  - Risk: Low
  - Confidence: Medium
  - CWE ID: 1004
  - WASC ID: 13

 - **Evaluate**
   - A cookie has been set without the HttpOnly flag, which means that the cookie can be accessed by JavaScript. If a malicious script can be run on this page then the cookie will be accessible and can be transmitted to another site. If this is a session cookie then session hijacking may be possible.
  
  - **Prevent**
    - Ensure that the HttpOnly flag is set for all cookies.


**Alert: Cookie Without Secure Flag**
- **Identify**
  - URL: [https://ibayaq.kedah.gov.my/](https://ibayaq.kedah.gov.my/)
  - Risk: Low
  - Confidence: Medium
  - CWE ID: 614

 - **Evaluate**
   - A cookie has been set without the secure flag, which means that the cookie can be accessed via unencrypted connections.
  
  - **Prevent**
    - Whenever a cookie contains sensitive information or is a session token, then it should always be passed using an encrypted channel. Ensure that the secure flag is set for cookies containing such sensitive information.

-------------------------------------------------------------------------------------------------------------------------------------------------------------------
# Information Disclosure

## Manual Scan only

**Alert: Information Disclosure - Suspicious Comments**
- **Identify**
  - URL: [https://ibayaq.kedah.gov.my/serviceworker.js](https://ibayaq.kedah.gov.my/serviceworker.js)
  - Risk: Informational
  - Confidence: Low
  - CWE ID: 200

 - **Evaluate**
   - The response appears to contain suspicious comments which may help an attacker. Note: Matches made within script blocks or files are against the entire content not only comments.
  
  - **Prevent**
    - Remove all comments that return information that may help an attacker and fix any underlying problems they refer to.


**Alert: Timestamp Disclosure - Unix**
- **Identify**
  - URL: [https://ibayaq.kedah.gov.my/](https://ibayaq.kedah.gov.my/)
  - Risk: Low
  - Confidence: Low
  - CWE ID: 200

 - **Evaluate**
   - A timestamp was disclosed by the application/web server - Unix
  
  - **Prevent**
    - Manually confirm that the timestamp data is not sensitive, and that the data cannot be aggregated to disclose exploitable patterns.

-------------------------------------------------------------------------------------------------------------------------------------------------------------------

## No alerts found in:
- Cookie Poisoning
- JS Library
- Secured Cookies
- CSRF
- Hash disclosure
