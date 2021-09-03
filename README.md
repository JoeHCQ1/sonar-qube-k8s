# SonarQubeInK8s
Example of SonarQube in k8s with postgre and AWS S3 for data backup.

## Structure

- [eks](./eks) Terraform workspace to provision AWS EKS cluster
- [k8s](./k8s) Terraform workspace to provision Kubernetes resources

## Prerequisites

This assumes you already have: 
- [Terraform](https://www.terraform.io/) [installed](https://learn.hashicorp.com/tutorials/terraform/install-cli?in=terraform/aws-get-started).
- [AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html) - recommend [autocomplete](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-completion.html)
- [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/)
- [kind](https://kind.sigs.k8s.io/docs/user/quick-start) (optional) useful for local k8s debugging

## Sources

- [Terraform Getting Started](https://learn.hashicorp.com/tutorials/terraform/infrastructure-as-code?in=terraform/aws-get-started)
- [Terraform EKS tutorial](https://learn.hashicorp.com/tutorials/terraform/eks)
- [Kubernetes provider tutorial](https://learn.hashicorp.com/tutorials/terraform/kubernetes-provider)

## Deploy Info

After initial deploy, you can get your kubeconfig so:
`aws eks --region $(terraform output -raw region) update-kubeconfig --name $(terraform output -raw cluster_name)`
