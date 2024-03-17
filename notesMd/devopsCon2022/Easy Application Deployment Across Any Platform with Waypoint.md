# Easy Application Deployment Across Any Platform with Waypoint - Yulei Liu, Staff Solutions Engineer at Hashicorp

## A History of Hashicorp

Hashicorp provides a software stack to provision, secure, connect and run apps.

Before we get into Waypoint, let's run the story back a bit to their other tools.

- Terraform: A tool to let you provision anything on any platform. Same workflow, wherever you plug it in.

- Packer: a packaging tool, for you to build packages wherever.

- Vault: secret management and protection platform, giving you a unified workflow for any cloud, any platform.

Hashicorp is popular because they try to unify a workflow that works for anything.

Companies use Hashicorp tools as an abstraction layer between infrastructure and it's users.

## What is Waypoint?

It provides a consistent developer experience, and a consistent operator experience, when managing the stack.

It is a higher level of abstraction then the other three tools.

It abstracts the stack into a single workflow, whether the underlying foundation is a HashiCorp tool stack, or any other patchwork of technologies.

Waypoint has 3 steps: Build (turn application source into an artifact), Deploy, Release.

You can use waypoint:
- From the CLI;
- From waypoint.hcl files (written in HCL or JSON);
- From the UI (lets you inspect projects, view their build and deploy history, execute commands and collect logs).

Main website: https://www.waypointproject.io/

Learn it: https://learn.hashicorp.com/waypoint

