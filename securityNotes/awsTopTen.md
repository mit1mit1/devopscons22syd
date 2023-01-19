# Top 10 Security Vulnerabilities (AWS)

## 1. Excessive Logging

### Example

Leaving `AWS_***` environment variables in the logged output when a request to a lambda fails when in a prod environment.

### Consequence

In the above case, full access to AWS resources through the console. Actual result varies based on what is being logged.

### Cause / Solution

Debugging a serverless application can be tricky, so it is often useful to add your own debugging to the response from a lambda. If you do, make sure to check that it is non-sensitive or else disabled in production.

## 2. Subdomain Takeover

### Example

Deleting an old S3 bucket leaves the bucket address available for others to use. A malicious actor could take the bucket name and impersonate you.

### Consequence

Reputable sounding web addresses - in fact, web addresses inside your domain - can be used by unrelated AWS users to host phishing attacks, steal cookies, etc.

### Cause / Solution

This can happen when an AWS resource is deleted without deleting the corresponding subdomain entry. To mitigate this threat, organization domains and providers must be catalogued, and incorrect or outdated subdomain references must be updated.

## 3. Misconfigured Reverse Proxy

### Example

NGINX is set up to forward from a public website to an internal website to allow for some urgent qa testing, but the location regex and proxy pass variable is open enough to allow NGINX to forward a user to AWS's Instance Metadata Service.  

### Consequence

Attackers can gain access to AWS secrets by querying them through the proxy.

Another potential, though probably less serious vulnerability - malicious actors could host their own websites and send victims a link to it through the proxy as part of a phishing attack.  

### Cause / Solution

This could happen whenever a proxy is left overly open. Solutions include: hiding the proxy itself behind a layer of authentication, or defining an "allow list" to limit where the proxy can redirect to.


## _To be continued_
