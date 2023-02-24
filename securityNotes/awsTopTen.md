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

## 6. Misconfigured AWS Cognito profile allows self-registration

### Context

_AWS Cognito_ is a service that handles customer identity and access management - i.e., you can use it to handle user authentication.

### Example

Cognito is used for a site that isn't meant for public access (e.g. internal company news site), but a flag is left on that allows people to create their own users.

### Consequence

Any secrets, confidential data, etc. visible on the website will be accessible to an attacker. In particular, note that even if a UI isn't provided to handle user creation, Cognito comes with an API which an attacker could use to create a user.

### Cause / Solution

If you're running a site that only some people should be able to access, configure Cognito to prevent self-registration.

## 7. Misconfigured AWS Cognito Attributes

### Example

A custom user attribute "custom:role" is set up in AWS Cognito and used to determine whether a user has access rights or not - however, the developers forget to set it as a read only attribute, so the user can set their own role through the AWS console.

### Consequence

Depending on what the attribute is that users get write access to, they might be able to access restricted sections of the site, perform restricted actions on the site, etc.

### Cause / Solution

If you're defining custom attributes (or using standard attributes to determine authorization in any way) you must make sure they are appropriately marked as read only.

## 7. S3 Directory Traversal

### Example

A lambda is set up which takes a user file, uploads it to S3, then displays it back to the user. To allow the user to see the file once it is uploaded, a token is returned to the user which gives them access to the file location on the S3. However, an attacker can pass a file with the name "../../", and the token they are returned will give them access to the entire bucket.

### Consequence

An attacker can gain access to anything on an S3 bucket.

### Cause / Solution

If you want to allow a user to see a file on an S3 bucket, make sure the file location is exactly where you want it to be. If you are interpreting user input to decide the file location, sanitize the user input appropriately first.

## 8. Weak S3 POST Upload Policy

### Example

An S3 bucket is used to store user image uploads, and also to store internal drivers and SDKs. The upload is done using AWS's browser-based file upload, and the base directory to upload to is not specified. 

### Consequence

An attacker can upload files to the S3 bucket to replace the drivers and SDKs, compromising behaviour.

### Cause / Solution

When allowing user upload to an S3 via the browser, always control the destination uploaded to - either by specifying the base directory, or by setting the file name it is saved in S3 as yourself.

## 9. S3 Bucket Authenticated Users 'WRITE' Access

### Example

An S3 bucket with static files used to load a page is meant to be public readable to everyone. However, the permissions have a wildcard Principle set ("*"), and have included this for both read _and_ write access.

### Consequence

An attacker can upload malicious javascript which will be executed when users visit your site.

### Cause / Solution

Again, be very careful with wildcard permissions on S3 buckets. If you don't need write access, turn it off. If you must have write access, restrict it as much as possible.

Again, tools exist to help with this - e.g. [Cloudsploit](www.cloudsploit.com).

## 10. Dangerous Dependencies

### Example

You run a site with NPM dependencies which have gone stale (known vulnerabilities are discovered in them).

An attacker may get access to your source code (e.g. through a directory traversal vulnerability on S3), and run `npm audit` on your source code to find vulnerabilities - alternatively they might just test a whole bunch of potential vulnerabilities.

### Consequence

Depending on the vulnerability in the dependency, the attacker might be able to do just about anything.

### Cause / Solution

You can't rely on obscurity to protect yourself against an attacker - automated attack tools exist and can attempt a range of attacks against a range of IP addresses very rapidly.

Hence, you must make sure you aren't vulnerable to common attacks, which are often due to known vulnerable dependencies.

Hence, you need to keep up with your `dependabot` alerts, etc.

## Bibliography

Thanks to [Kontra](https://application.security/free/kontra-aws-clould-top-10) for providing the course these notes are based off.