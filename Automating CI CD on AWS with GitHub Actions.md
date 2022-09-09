# Automating CI/CD on AWS with GitHub Actions - Derek Bingham, Senior Developer Advocate of AWS

(Derek has 20 years in software dev, 4 years at AWS - he's from Belfast)

## The joy of infrequent releases.

As time between releases increases, so does pain. A user with a bug in your software for 4 months will stop using your software.

But how do we reduce that time? As a community, we've adopted automation, we automate everything.

That comes with challenges, because there's a lot to automate - compile, build, test, lint, build infrastructure, deployment, compliance checks, deploy the actual code.

All these different things to deploy means we need choices, as no one tool can be the best of breed at all of that. This, we need to pick the best orchestration tool, container registry, security compliance checks.

## Plans for this session

For this session, we'll set an automation challenge. We want a flask app running in a container, deployed to AWS cloud, able to deploy regular releases, using our preferred orchestrator GitHub actions. We'll also demonstrate why flexibility is key as we cope with changing requirements.

Amazon ECR is a place to store container images used for build and deploy (it can compliance check them too).

AWS offers EKS for kubernetes containers, ECS for others - AWS Fargate sits as an abstraction layer on both, we'll use that.

AWS CDK allows us to do infrastructure as code in a higher level language than JSON or yml. It lets us do loops, use variables and even write unit tests on our IaC easily. That's pretty nice.

We will implement complex orchestration and CI/CD functionality on GitHub with GitHub Actions. You can actually do more complex there than you'd think.

You can use actions provided from GitHub, you can also do actions provided by AWS at 'aws-actions/…'

## Demo

Our task definition in a JSON file tells Fargate what to do - the GitHub actions we use are all available with examples on the GitHub marketplace.

Secret keys are managed on GitHub easily enough.

We go through a quick set up of flask app, simple pipeline on GitHub.

That's good, but what if requirements change? Say we no longer want to run the tests on GitHub, but instead want to run the tests on AWS to reduce the blast radius. We say good, let's use AWS CodeBuild.

Now when we push to GitHub, we have a CodeBuild agent listening to the branch, and it will run tests or whatever, and will then say back to GitHub actions "passed, clear to continue".

Demo of setting up with CodeBuild. Seems to work fairly similar to Buildkite?

Moral of the story, there's more than one way to skin a cat.
