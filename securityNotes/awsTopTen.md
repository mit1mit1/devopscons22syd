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

## 4. Lambda XML External Entity Injection

### Example

A lambda is set up to upload a users Google Doc, parse it, and populate the page from it. A malicious actor can upload an XML doc which references external data, e.g. the lambda itself. Lambda code, etc. can then be shared with the page.

### Consequence

Attackers can inject their own commands into a lambda XML parser, which can then give them access to lambda resources/code, which may in turn give them access to DB secrets, etc.

### Cause / Solution

XML parsers, when used to parse untrusted XML files, must be sufficiently restricted so that they can't parse external entities and document type definitions.

## 4. Lambda Command Injection

### Example

A lambda is set up to upload user files and output scanned information. However, the scan is performed through a command line script using exec, and the file name is not sanitised.

### Consequence

In this particular case, attackers could upload files with malicious names - e.g. names that end the line early, then run command line scripts that send AWS credentials to the attackers server.

In general, once a lambda allows user input to be run on the command line, you're fully compromised.

### Cause / Solution

This can occur whenever user input is passed to calls that interact with the system environment.

To mitigate, ensure user input is validated against an allowlist, or similar (e.g. only alphanumeric characters) before allowing it to interact with the system environment.

## 5. S3 Bucket  with 'Read' Access

### Example

Misconfigured S3 bucket has `Principle: *`, meaning unidentified users can access it freely.

### Consequence

Any secrets, confidential data, etc. stored in the bucket will be accessible to an attacker.

### Cause / Solution

This can occur when the ownership of the bucket is too broad by accident, or a bucket that is meant to be public has secrets added to it.

To prevent, make sure your bucket policies are as strict as possible (have an IP address allowlist as well if possible) for any buckets that contain non-public resources.

You can use automated tools to identify issues like this too (Snyk, etc.).

## _To be continued_


## Bibliography

Thanks to [Kontra](https://application.security/free/kontra-aws-clould-top-10) for providing the course these notes are based off.