# Loved by Developers, Trusted by Enterprises: How to Manage Jenkins at Scale - Paul Yang, Senior Architect of CloudBees

Paul from CloudBee, where everyone loves Jenkins.

Why is it always CloudBees talking about Jenkins? Because they are the #1 contributor. They commit 80% of the Jenkins code.

What is Jenkins? It has developed into a mature architecture system, with 1800+ plugins. It is a flexible architecture.

If you are a startup developer, you'll be pretty happy with open-source Jenkins as is. But as a enterprise level company, you'll need to scale it. Two possible approaches -

1. Scale out into islands of Jenkins, where different teams each have their own Jenkins. They have their own Jenkins expertise - or at least they better, otherwise the DevOps might have troubles.
2. Scale up into a Jenkinstein, where all teams have a single, centralized server, security, compliance controls. Scalability is an issue though, configurability and performance with have issues.

Transparency issues, stability issues and support issues all happen at scale.

This is where CloudBee comes in. They provide scalable, central management with autonomy. They give an operations center which can provide Jenkins controllers (instances), which can be deployed on Bare metal, VMs, containers, ...

It uses the power of kubernetes. Users hit ingress, which is part of the kubernetes master, chose api server to makes nodes (Kubernets) which have operations centre.

This solves much of the issues with islands of Jenkins/Jenkinstein.

Moreover, CloudBees will manage the plugin management (it is better when this is left to experts at scale). The CloudBees assurance program with Beekeeper will keep that running nicely.

Cluster operations lets you centrally manage all Jenkins instances (some customers have 100s of Jenkins instances). Plugin and controller management can all be handled from the operations centre. Visibility is thus managed.

Managed controller hibernation puts Jenkins masters to sleep if they are idle, giving efficient infrastructure usage.

The flexible Role-Based Access Control at the global level of the CloudBee CI gives roles, groups and user, and lets you grant access rights at top, folder, individual controller or object levels. This handles security.

Jenkins already empowers developers, CloudBee CI takes it further.

Most importantly, it provides configuration as code. You can manage the controllers and masters in the GitOps way, using yaml files. E.g. you can define controller specific behaviour and plugins based on the language they're dealing with, and deploy it with a git push.

Freestyle jobs can be converted to declarative pipelines with ease. Your experts can also create templates for the developers, and put them in catalogs.

Why use CloudBees over open-source Jenkins? Resiliency, bunch of other stuff (see slide)

CloudBees is more than Jenkins. They provide CloudBees Continuous Delivery/Release Orchestration which is a single tool for build and release, with visibility on all of it.

CloudBees works with global CSPs in support of mutual customers.
