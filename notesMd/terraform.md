# Miscellaneous Resources: Terraform

## [Terraform explained in 15 mins](https://www.youtube.com/watch?v=l5k1ai_GBDE&ab_channel=TechWorldwithNana) (TechWorldwithNana):

- Video summary of what terraform is (in comparison to Ansible) and how it works.
- Terraform is best at infrastructure provisioning.
- It is declarative rather than imperative - you describe the desired end state in your `tf` files, and terraform handles how to get there.

## [Terraform tips & tricks: loops, if-statements, and gotchas](https://blog.gruntwork.io/terraform-tips-tricks-loops-if-statements-and-gotchas-f739bbae55f9)

- Detailed write up on conditionals and loops in terraform
- Terraform doesn't support conditionals natively - instead, you can use count, foreach, or for.
- However, each of these comes with tweaks to how resources are declared and restrictions to what they can do.
