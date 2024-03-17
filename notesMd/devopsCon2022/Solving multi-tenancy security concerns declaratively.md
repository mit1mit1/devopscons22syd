## Solving multi-tenancy security concerns declaratively - Kasun Talwatta, Field Engineer at Solo.io

Solo has a huge customer base. They're there to develop subscription solutions to application networking challenges.

Definition of multi-tenancy: efficient use of infrastructure while providing robust isolation of products.

Benefits of Multi-tenancy:

- Reduces operational cost and complexity;
- Accommodates trusted and untrusted tenets;
- Forces you to optimise a bit.

Current state of multi-tenancy in Kubernetes:

- You use namespaces, bunch of other Kubernetes specific stuff.
- You can use tech such as vCluster or VirtualCluster to solve the issue of multiple boundaries (and some other issues) for you.
- Or you can just have a Kubernetes cluster per tennant (not cost effective at scale). Not many people do this, but it does provide full isolation.

What if you want to manage boundaries across cloud service providers?

Istio (/service mesh) allows you to define policies for service isolation, while focussing heavily on your business logic. You don't have to focus on cross cutting, security, or observability as much - it solves that for you.

Implementation of some models for dealing with multi-tenancy are in the slides (bit beyond me, and far beyond my ability to notate).

Why should you need to expose Kubernetes API for discovery and compromise?

Alternatively, create a management plane on top of the service meshes (described on last slides).
