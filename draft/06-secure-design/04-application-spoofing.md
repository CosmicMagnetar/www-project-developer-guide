---

title: Application Spoofing
layout: col-document
tags: OWASP Developer Guide
author:
contributors:
document: OWASP Developer Guide
order: 604

---

{% include breadcrumb.html %}
### 6.4 Application Spoofing

The OWASP Development Guide is being rewritten by the OWASP community.
and the content of this section has yet to be filled in.

If you would like to contribute then follow the 
[contributing guidelines](https://github.com/OWASP/www-project-developer-guide/blob/main/CONTRIBUTING.md)
and submit your content for review.

The following subsections are planned:

  * Application spoofing
    * domain squatting
    * typo squatting

Application spoofing:
What is application spoofing: 
* A threat actor including an application in a malicious iFrame
* A threat actor creating dependencies with similar names as legitimate ones (typo squatting)

How can it be addressed:

Application spoofing / clickjacking

Set X-FRAME-OPTIONS header to SAMEORIGIN or DENY, depending on what the business requirement is for rendering the web page.
This will help prevent a malicious actor including your application in an iFrame to capture credentials/exfiltrate data. As a caveat, this will not work with Meta Tags. X-FRAME-OPTIONS must be applied as HTTP Response Header

Use Content Security Policy:
Common uses of CSP frame-ancestors:
Content-Security-Policy: frame-ancestors 'none';
               This prevents any domain from framing the content. This setting is recommended unless a specific need has been identified for framing.
Content-Security-Policy: frame-ancestors 'self';
              This only allows the current site to frame the content.
Content-Security-Policy: frame-ancestors 'self' *.somesite.com https://myfriend.site.com;
              This allows the current site, as well as any page on somesite.com (using any protocol), and only the page myfriend.site.com, using HTTPS only on the default port (443).

Use SameSite Cookies

Use httpOnly cookies



Domain squatting / typo squatting

What is domain squatting (also known as cybersquatting): 
* A threat actor creating a malicious domain with the same spelling as a legitimate domain but use different UTF characters (domain squatting)
* A threat actor registering, trafficking in, or using an Internet domain name, with an intent to profit from the goodwill of a trademark belonging to someone else.
* Though domain squatting impacts brand value directly, it has an impact from a security perspective.
* It can result in the following kind of scenario: (also known as typosquatting)



Wherein the domain with U+00ED may be a malicious application trying to harvest credentials. 
* Typo squatting is achieved with supply chain manipulation. 

How can it be addressed:

* Use threat intelligence to monitor lookalikes for your domain
* In the event a dispute needs to be raised, it can be done with URDP:
https://www.icann.org/resources/pages/help/dndr/udrp-en 

* Verify packages in registries before using them




