# Top 11 Security Vulnerabilities (NodeJS)

## 1. Improper Assets Management

### Example

Leaving an old version of an API endpoint open and unmaintained, so security updates applied to the v3 don't help the v1.

### Consequence

Could be as serious as leaving the "password reset" endpoint open without protecting it from brute force attempts.

### Cause / Solution

Keep track of your APIs and their versions, ideally with good documentation. Turn off endpoints that are no longer in use.

## 2. Broken Object Level Authorization

### Example

An API endpoint will return user information if you have the user id, without checking if you are authorized to view that user.

### Consequence

PII leak.

### Cause / Solution

It might be assumed that since the frontend will only pass the user id of the logged in user, we can assume the API will only receive the user id of the logged in user. Need to remember APIs are accessible to an attacker, and appropriately restrict their behaviour.

## 3. Excessive Data Exposure

### Example

A "Password Reset" response includes the reset token.

### Consequence

Attackers can gain access to credentials/data they shouldn't have access to.

### Cause / Solution

It is easy to assume that what is visible in the UI is all the user has access to, but you need to be careful about anything you return in a response.

## 4. Broken User Authentication

### Example

2FA is set up for your app, but the 2FA simply requests a numeric token that is not protected from a brute force attack.

### Consequence

Attackers can log in as any user whose credentials have been leaked in a data breach.

### Cause / Solution

Make 2FA stronger, by adding a limit to attempts, a capture, or using a longer numeric token.

## 5. Lack of Resources and Rate Limiting

### Example

No restriction on how many "Sign Up"'s an IP address can attempt.

### Consequence

If meaningful data can sometimes be attained from the resource that is not restricted, a brute force attack can guarantee it will be attained.

In this example, if the Sign Up response tells you that an email address is taken, an attacker can enumerate emails to find out who has signed up to the service.

### Cause / Solution

The solution is to limit the availability of public APIs.

In this particular example, it's also good practice to give a generic response to a sign up failure, e.g. say an email has been sent to that address either way.

## 6. Broken Function Level Authorization

### Example

No restriction on who can call an API endpoint.

### Consequence

Depending on the API endpoint, data leakage or data corruption.

### Cause / Solution

This vulnerability is most likely when creating a 'hidden' API endpoint. However, just because it is not used by the frontend doesn't mean an attacker can't guess what it is, and abuse it.

Solution - enforce authorization checks on every API endpoint unless it is known to be safe for public use.

## 7. Mass Assignment

### Example

"Update Password" endpoint allows other fields including userRole to be updated.

### Consequence

Depending on the API endpoint, a malicious actor could force admin access.

### Cause / Solution

API schemas should be explicitly defined rather than blindly accepting any object property.  

## 8. Security Misconfiguration

### Example

Failing to set `X-Frame-Options` or `Content-Security-Header` allows malicious actors to set an iframe over your website and execute a click-jacking attack.

### Consequence

User accounts can be compromised, and everything that follows can go wrong.

### Cause / Solution

Apply appropriate content security policies to your site.

## 9. SQL Injection

### Example

Login accepts an IP address param which is used in an SQL statement without sanitization.

### Consequence

Data leakage and corruption.

### Cause / Solution

This is possible whenever user input is passed to SQL. User input should always be sanitised and used in a prepared SQL statement instead of passed to SQL directly.

Note: There are Open Source tools that help find SQL injection points by allowing detailed SQL error responses to be returned from a web endpoint (browsers normally cut the error responses out).

## 10. Insufficient Logging & Monitoring

### Example

Session use is not recorded.

### Consequence

Unable to determine whether a malicious actor has used a compromised token.

### Cause / Solution

Make sure you log user sessions and/or actions somewhere.

## 11. XML External Entity Injection

### Example

Users can upload spreadsheets, the XML parser for these is weak.

### Consequence

Malicious actor can force the server to execute arbitrary XML, e.g. logging passwords.

### Cause / Solution

This can occur when your XML parser allows the inputted XML file to set the doctype. Ideally, disable this, and disable the loading of external entities.

## Bibliography

Thanks to [Kontra](https://application.security/free/kontra-aws-clould-top-10) for providing the course these notes are based off.