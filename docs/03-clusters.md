# EKSaC Cluster Components

## Introduction
The cluster components for EKSaC manages the followings:
- The _IAM roles_ required for EKS cluster
- The _security groups_ for
  - EKS control plane with
    - Allow ingress from EKS nodes on port 443
    - Allow egress to EKS nodes on ports 1024 - 65535
  - EKS nodes with
    - Allow ingress from other nodes on all ports
    - Allow ingress from EKS control plane on ports 1025 - 65535
    - Allow egress for all
- Access entries (moving away from `aws_auth` _configMap_) for cluster access
- Essential Managed AddOns
  - AWS EBS CSI driver with associated _IAM role_ and _IAM policies_ as well as the _pod identity association_
  - AWS pod identity agent
- Create OIDC provider for the clsuter

## TODO
1.  _Tags_ to be updated from _XR_ instead of hard-coded
1.  Check the communication requirement for EKS control plane and nodes and tighten the ingress / egress rules
1.  Consider moving away from EKS Managed AddOns to _helm_ install
