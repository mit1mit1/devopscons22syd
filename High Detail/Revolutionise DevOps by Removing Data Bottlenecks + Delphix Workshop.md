# Revolutionise DevOps by Removing Data Bottlenecks - Andrew Hinde, Regional Manager at Delphix

This talk is about leading with DevOps and compliance to achieve your organisational goals.

Context: my daughter currently has a goal to become a better surfer by the end of the year. As a surfer, I think I can help with this more than with her previous ballet goal.

This is related to leading with DevOps. You need commitment to make it work. But why lead with compliance?

20 years ago, only 1 of the top 5 companies were tech. 10 years ago, 2 were. Now all of the top 5 companies are.

What's fuelling this radical growth? Why can't the other companies keep up?

Gene Kim says that "This is not a story about small beating large; it's fast beats slow. According to the data, the highest performing organisations are better at speed, quality and security."

High performers are fast and organised, with thousands of deployments per day - others are only deploying 2 to 12 times a year. This has let them bypass categories, move from books to retail, search engines to everything else.

Why does devops do this? What trends help it?

1. It moves from slow to fast application releases. Waterfall might give monthly releases, agile required weekly, devops asks for daily.
2. Applications are modernised from traditional datacenter to multi-cloud - because automation of the infrastructure requires this, and speeds things up heads.
3. Automation of code
4. High trust to zero trust - bad guys want to steal your stuff, good guys want to find non-compliers, so you can't trust anyone or anything (T-Mobile is a instructive case, developers were responsible for identifying and hiding information, they gave the credentials to ransom gangs, 50 million customers personal info goes).

Data is the last devops frontier. Where to focus on improving? The bottleneck. And data is the bottleneck.

Automate infrastructure for delivery speed. This is done by most organisations.

Automate the code. Also already done by most organisations.

Automate the data - delivery and privacy of it. This is rarer.

Joseph runs engineering at a company, uses Delphix as part of the pipeline. They spun up 1700 new test environments in a day with Delphix.

An oil company used delphix to rapidly improve CX while complying with global data protection regulations.

Delphix can serve up fast data, from 48 hours to 1, for high quality software releases. 70% saving on storage of data.

Another company reduced "good data" provision for dev from 3+ weeks to < 1 hour speeds DX innovation cycle with Delphix.

Driving transformation at a massive scale. the transformation was enormous. They needed to automate everything like they used to automate code, and data was the last thing to go. The non-prod data defects have dropped by 70% since that, they allowed users to self serve data. Developer productivity went from 20% to 75%. Deployment times have gone from quarterly to multiple daily.

Improved provisioning time from months to minutes, increased infrastructure provisioning through self-service.

# Workshop

# DevOps Data Automation with Delphix

## Q. What about PII?

There's an automated discover process, but you can absolutely bake in the logic for how to find PII and how to mask or transform it. There's flexibility there for you to put in your business logic.
Moreover, you can do this at either a metadata or data level (metadata will be a very quick search, data will be slower). You can also decide how far or deep to go in the dataset so you can just do a 15% data smoke check to start with.

You can of course do both metadata and data.

There can of course still be false positives - Postcodes and DOBs, are classics. You can tell the search what the metadata structure looks like to make the search more specific.

## Back to the talk:

How can we help with the devops process? Well, do you find data is an issue in the CI/CD? Do you deal with live data there? Do you need to?

Data is never part of CI/CD in general. "If the code works and there's no bug in it, woohoo". Delphix helps you get data along side your builds in CI/CD. Code is never truly bug free, so you want to test it against real (but masked) data.

How does this work?

1. It captures a snap of production data, puts it into the continuous data engine. There's immutable data there, which is then mirrored by teams, and the mirrors get changed. Hence, the mirrored 'copies' are very small, as only changes are recorded (same concept as Docker (though it is a lot older than Docker)).
2. Now, from Prod, the data can be masked. You may or may not want to do this - you can build a production fix database of unmasked data, or a test dataset of masked data (i.e. one with PII obscured/altered).
3. It is also bookmarked.
4. Freeze the data, do post-processing activity, bookmark.
5. Refresh the QA and DEV from MASK

## Continuous compliance.

Automated sensitive data discovery, masking with multi-cloud referential integrity. You can always alter the randomiser for the each run. So in a run, there will be consistent transformation of the same PII, but on the next run, it will be different. You can achieve this by passing in a different automatically generated key on each run.

## DevOps TDM Enables Digital transformation

Very impressive money and time numbers.

## Live demo of UI Element

(There is also an extensive API, which can do everything the UI can do).

Plugins available on the management console, where you can enhance Delphix capability to cover more databases.

Then you can add environments (hosts or clusters of servers that Delphix can talk to). You just tell it the connection and login details, and Delphix goes from there.

Once that's done, you can look at the datasets. You can make them inactive or active.

## Delphix Automates Data in DevOps Pipelines

Delphix integrates at multiple levels.

- Code: With servicenow and Jira
- CI: With Terraform, Ansible, ProgressChef, puppet, Jenkins and docker. Sometimes you might want test data for unit tests - can be done. Normally you'll want it for integration tests - main use case. It's all API calls, so you can embed them inside the progress anywhere. As we hear more from the customers, we add more integrations. There's also a toolkit provided so you can integrate with any tool of your choice, using SDKs. We're still adding more and more support, but you don't need to wait.
- CD: We don't integrate here, you don't want to push the data.
- SRE: Delphix integrates with dynatrace, New Relic, AppDynamics. Deliver data when issues occur to recover rapidly.

## An example flow demonstrating integration with GitHub

1.  Commit code to GitHub. This triggers a Jenkins automation.
2.  Jenkins builds code then executes Terraform Job.
3.  Terraform provisions environment with cloud and Delphix providers.
4.  AWS spins up the cloud, Delphix provisions the data.
5.  Use it

## Provide self-service access to a test data library

You can do this in a consistent fashion so any user can take a bookmark and spin up their own branch using the test data. You can:

- Ingest data from multiple production sources
- Mask and manipulate test data
- Curate virtual copies and provide self-service access

Key benefits:

- Eliminate data wait times to accelerate test cycles.
- Test against the _right_ dataset for more productive test cycles.
