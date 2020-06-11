# Content Security Policy (CSP)

* Content Security Policy (CSP) is an added layer of security that helps to detect and mitigate certain types of attacks, including Cross Site Scripting (XSS) and data injection attacks. These attacks are used for everything from data theft to site defacement to distribution of malware.

* CSP is designed to be fully backward compatible. Browsers that don't support it still work with servers that implement it, and vice-versa: browsers that don't support CSP simply ignore it, functioning as usual, defaulting to the standard same-origin policy for web content. If the site doesn't offer the CSP header, browsers likewise use the standard same-origin policy.

To enable CSP, you need to configure your web server to return the `Content-Security-Policy` HTTP header


Refer This : [CSP](https://developer.mozilla.org/en-US/docs/Web/HTTP/CSP)
