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

For. Net applications check that the views tate is signed and encrypted.

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

Secial characters accepted as input

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
