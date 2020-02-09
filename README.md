# Appseclist
Cache-Control: no-cache, no-store, must-revalidate

robots meta tag
<Meta name="robots" content="noindex" />
(for html content in html <head> section) 

X-Robots-Tag: noindex
(for pdf, images etc sent as httpheader)

Look for source code comments having usernames and password, developer names, defect numbers, path to server side resources. Make sure sensitive info is encrypted or masked so that full values do not appear in response or ui. 

Look for encryption keys or insecure cryptographic storage.

Check for server side code in responses, such as may be found in <% tags like this %>

Sensitive information passed in get request or in query string of a post.

For. Net applications check that the views tate is signed and encrypted.(Proxy Required)

Check to see private email are not disclosed in html source.

Check responses for disclosure of internal ip addresses.

Check for cross site script inclusion (xssi) by looking for scripts or other active content(such as Google analytics) that loads from non organisational systems.

Check for a /crossdomain.xml and  a /client accesspolicy.xml, make sure they do not allow crossdomain requests from third party servers.

Check http response headers for cors misconfigurations with acao= origin reflection or acao=* or acao= null

Try to retrieve wsdl file from server, by guessing common locations and calling conventions such as adding '?wsdl' at the end of a path, using '.wsdl' as the file extension, or looking for /wsdl/ directory.

Review the Http response headers looking for anything that discloses info about the server and its environment. Always look for "server" and "X-Powered-By" headers, but be alert for other disclosures in other less common headers.

Check for Persistent Auth in response header which should not be set to true. 

Check for insecure use of "X-Forwarded-For" 

Check for info leakage through 'robots.txt'

Https to http 

Password policy if registration page is there. 
Password length
Password complexity 
Password history

Special characters accepted as input

Remember me function should not be there in case of financial application. 

Autocomplete should be off in form source code. 


Password change functionality for a user should verify old password and then allow password to change. 
Verify username is not a part of password change request, if it is try substituting another valid username. 

Check if an internal URL can be accessed without authentication. 
Also check Privilege escalation horizontal and vertical. 

Back refresh attack

Verify that any sensitive info is encrypted or masked so that full values do not appear

Account lockout test 

Account unlocking function can it be bypassed

Test for captcha 

Username enumeration on login page (there should be generic error msg) 

Username enumeration on forgot password functionality 
Cookie replacement or sso ticket /token replacement or manipulation test. 

Privilege horizontal and vertical escalation by URL manipulation, parameter, cookies, headers, request manipulation. 

Look for hidden/disabled links/functionality in response try to access them

Test logout functionality Session should terminate. 


Idle session timeout test (15 minutes) 

Verify Concurrent logins, check last login timestamp being displayed to users

Test Session fixation attack by using another session ID (unused) 
Check to see if session Id changes after authentication 


Session Hijacking > use xss if you can to demo cookie stealing and then set that cookie into a new browser using a cookie editor or developer tools in a new browser.

Test Logout functionality.

Cookies without expiration time should not have sensitive data.
Persistant cookies check use about:cache? storage=disk&context=
In mozilla

Verify that Set-Cookie headers include secure and httponly flags and path is set to application root not webserver root. 

Check to see if cookies are controlling user privileges try to escalate privileges using cookies 

Compare one users cookies to another users look for similarities that may expose info

Check that cookies are deleted from browser on Logout, by a Set-Cookie header with a null or meaningless value. 

Session puzzling: verify if application provides access to internal functionality or pages after accessing anonymous functionality like forgot password. 

Client side session defenses: session timeout or termination on Web browser close event. 
On idle session timeout event check for Redirection to login page or the same resource which is presented on Logout. 

Input validation: format, length, type(data type) and range

Omit parameters from requests and note applications response. (use a proxy to intercept and omit parameters) 

Send parameters with null values and note the applications response( use proxy) 

Send parameters or cookies with extremely long values to be sure they are handled gracefully. (use proxy) 

Http parameter pollution: Send duplicate parameters, custom pRameters and note the applications response. (proxy) 

Test for POST REQUEST  as GET and make sure server does not process it. (proxy) 

Test for GET request as HEAD which requires authentication is not treated differently. (Proxy)

Test for xss reflected/stored, Dom based 

Check for ui redress aka clickjacking> anti click jacking header is present or not, frame busting code is present or not. 

Test for sql injection 

Test for host header injection by replacing host request  header value with a malicious one try bypass validation by adding malicious domain in addition to original domain etc. (proxy) 

Test for os command injection(proxy) 

Test for Xml external entity in case website is processing Xml (proxy) 

Remote or local file inclusion

File upload test cases
File extension check(malicious extension, multiple extensions and null byte extensions) 
File size check
Anti-virus scanning
Test for ability to retrieve uploaded file (rce) 
Unvalidated redirects and forwards

Http response splitting

Http server error 500

Check for Eval() function in client side code(js). Verify that user-controlled input is not passed to this function call. 

Outdated 3rd party software> if you found out the version number of any component search the Web for any vulnerabilities reported against that version

Default credentials have been disabled

Look for config files that should not be accessible, such as global.asax, Web.xml,.htaccess, Web.config, app.config, etc. 

Verify Directory listing or directory indexing is disabled. /images is a good place to start. 

Check for hidden directories based on target platform. 

Check for alternate versions of files by altering file extensions. 

Check for application test pages or scripts by common names ( eg. Test. Aspx) or by altering legitimate resource names. 

Check for path traversal by requesting things such as... /.. /.. /.. /.. /.. /etc/paswd or ../../../../../boot.ini

If web server is apache 
Check for EXPECT header XSS
Check for request method XSS by sending a script in place of request verb. 
Check to see /server-status is not enabled. 
Check to see /server-info is not enabled. 

Verify dangerous http methods are disabled. 
Only GET, HEAD and POST should be enabled. 
Send OPTIONS request to any known resource, and test any methods that server says are enabled. 
Also test, TRACE, PUT and DELETE, regardless of what OPTIONs report. 
Also test DEBUG to make sure remote debugging is disabled for .net applications. 
Also test, PROPFIND, CONNECT, COPY and other http methods. 

Ensure content-type and charcterset are correctly stated in responses.
