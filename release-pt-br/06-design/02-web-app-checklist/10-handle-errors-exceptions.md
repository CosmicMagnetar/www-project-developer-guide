---

title: Handle all Errors and Exceptions Checklist
layout: col-document
tags: OWASP Developer Guide
contributors:
document: OWASP Developer Guide
order: 26300
permalink: /release-pt-br/design/web_app_checklist/handle_errors_and_exceptions/

---

{% include breadcrumb.html %}

### 4.2.10 Checklist: Handle all Errors and Exceptions

Handling [exceptions and errors][cserror] correctly is critical to making your code reliable and secure.
Error and exception handling occurs in all areas of an application including critical business logic
as well as security features and framework code.

Refer to proactive control [C3: Validate all Input & Handle Exceptions][control3]
and its [cheatsheets][csproactive-c10] for more context from the OWASP Top 10 Proactive Controls project,
and use the list below as suggestions for a checklist that has been tailored for the individual project.

#### 1. Errors and exceptions

1. Manage exceptions in a centralized manner to avoid duplicated try/catch blocks in the code
1. Ensure that all unexpected behavior is correctly handled inside the application
1. Ensure that error messages displayed to users do not leak critical data,
    but are still verbose enough to enable the proper user response
1. Ensure that exceptions logs give enough information for support, QA, forensics or incident response teams
1. Carefully test and verify error handling code
1. Do not disclose sensitive information in error responses, for example
    system details, session identifiers or account information
1. Use error handlers that do not display debugging or stack trace information
1. Implement generic error messages and use custom error pages
1. The application should handle application errors and not rely on the server configuration
1. Properly free allocated memory when error conditions occur
1. Error handling logic associated with security controls should deny access by default

#### References

* OWASP [Code Review Guide: Error Handling][review]
* OWASP [Improper Error Handling][handle]
* OWASP [Top 10 Proactive Controls][proactive10]

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue060210] or [edit on GitHub][edit060210].

[cserror]: https://cheatsheetseries.owasp.org/cheatsheets/Error_Handling_Cheat_Sheet
[csproactive-c10]: https://cheatsheetseries.owasp.org/IndexProactiveControls.html#c10-handle-all-errors-and-exceptions
[control3]: https://top10proactive.owasp.org/the-top-10/c3-validate-input-and-handle-exceptions/
[edit060210]: https://github.com/OWASP/www-project-developer-guide/blob/main/draft/06-design/02-web-app-checklist/10-handle-errors-exceptions.md
[handle]: https://owasp.org/www-community/Improper_Error_Handling
[issue060210]: https://github.com/OWASP/www-project-developer-guide/issues/new?labels=enhancement&template=request.md&title=Update:%2006-design/02-web-app-checklist/10-handle-errors-exceptions
[proactive10]: https://top10proactive.owasp.org/
[review]: https://owasp.org/www-project-code-review-guide/