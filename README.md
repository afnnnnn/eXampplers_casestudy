# eXampplers_casestudy


## Table of Contents
1. [Group Members]
2. [Task Distribution]
3. [Brief Description]
4. [Automated Scan]
    - [Alert 1]
    - [Alert 2]
    - [Alert 3]

## **Group eXampplers**
- Afnan Iman bin Azman (1920311)
- Sharul Irfan bin Sharul Isram (1921825)
- Hazim

## **Task Distribution
-Afnan
-Sharul
-Hazim

Case Study website: https://ibayaq.kedah.gov.my/

## **Description**

iBayaq is a website that aims to facilitate and speed up the payment of various type of revenue to the Kedah State Government such as land tax, housing bill collection, education loan repayments and entrepenuer loans. The aim of this case study is to identify the vulnerabilities present in the iBayaq site, evaluate them and how to prevent the vulnerabilities from happenning again.



--------------------------------------------------------------------------------------------------------------------------------------------------------------------

## **Automated scan:**
4 orange flags, 4 yellow flags, 5 blue flags

### **Alert no 1: CSP**

Risk level: Medium

Confidence: High

### Identification:
-  CSP: Wildcard Directive
-  CSP: script-src unsafe-eval
-  CSP: script-src unsafe-inline
-  CSP: style-src unsafe-inline
                       
 ### evaluation
  -  **CSP:**
     Content Security Policy (CSP) is an added layer of security that helps to detect and mitigate certain types of attacks. Including (but not limited to) Cross Site Scripting (XSS), and data injection attacks.
     
  -  **CSP: Wildcard Directive:**
     allows resources of this type from anywhere as long as they're not explicitly restricted by other directives.
     
  -  **CSP: script-src unsafe-eval:**
     The unsafe-eval value in the script-src directive of a Content Security Policy (CSP) indicates that scripts can be executed with the ability to use eval() and similar dynamic code execution functions.
     
  -  **CSP: script-src unsafe-inline:**
      unsafe-inline value in the script-src directive of a Content Security Policy (CSP) indicates that inline JavaScript code (code directly embedded within HTML) is allowed to be executed.
     
  -  **CSP: style-src unsafe-inline:**
     The unsafe-inline value in the style-src directive of a Content Security Policy (CSP) indicates that inline CSS styles (styles directly embedded within HTML) are allowed to be applied.

### prevention
Ensure that the web server, application server, load balancer, etc. is properly configured to set the Content-Security-Policy header.


### **Alert no 2**

Risk level: Low

Confidence: Medium

### Identification:
-  Cookie No HttpOnly Flag
-  Cookie without Secure Flag
-  Cross-Domain JavaScript Source File Inclusion
                       
 ### evaluation
  -  **Cookie No HttpOnly Flag**
     A cookie set without the HttpOnly flag, which means the cookie can be accessed by Javascript.
     If a malicious script can be run on this page then the cookie will be accessible and can be transmitted to another site. If this is a session cookie then session hijacking may be possible.
     
  -  **Cookie without Secure Flag**
     A cookie has been set without the secure flag, the cookie can be accessed via unencrypted connections.
     
  -  **Cross-Domain JavaScript Source File Inclusion**
     The page includes one or more script files from a third-party domain.


### prevention
  -  Cookie No HttpOnly Flag: Ensure that the HttpOnly flag is set for all cookies.
  -  Cookie without Secure Flag: Whenever a cookie contains sensitive information or is a session token, then it should always be passed using an encrypted channel. Ensure that the secure flag is set for cookies containing such sensitive information.
  -  Cross-Domain JavaScript Source File Inclusion: Ensure JavaScript source files are loaded from only trusted sources, and the sources can't be controlled by end users of the application.


### **Alert no 3**

Risk level: Low

Confidence: low

### Identification:
-  Timestamp Disclouse-Unix
                       
 ### evaluation
-  A timestamp was disclosed by the application/web server - Unix


### prevention
- Manually confirm that the timestamp data is not sensitive, and that the data cannot be aggregated to disclose exploitable patterns.
-------------------------------------------------------------------------------------------------------------------------------------------------------------------



**Manual scan:** 
8 orange flags, 7 yellow flags, 5 blue flags

Identification:



evaluation
prevention
