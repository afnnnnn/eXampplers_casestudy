# eXampplers_casestudy

Group eXampplers
- Afnan Iman bin Azman (1920311)
- Sharul Irfan bin Sharul Isram (1921825)
- Hazim

Case Study website: https://ibayaq.kedah.gov.my/
-Description-

--------------------------------------------------------------------------------------------------------------------------------------------------------------------

## **Automated scan:**
4 orange flags, 4 yellow flags, 5 blue flags

### Alert no 1: CSP
Risk level: Medium
Confidence: High
###Identification:
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

--------------------------------------------------------------------------------------------------------------------------------------------------------------------



**Manual scan:** 
8 orange flags, 7 yellow flags, 5 blue flags

Identification:



evaluation
prevention
