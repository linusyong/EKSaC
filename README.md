# EKSaC
EKS as Consumables

# Misc
- https://repeatit.io/ for go templating
- ```
  aws ec2 describe-instances --profile sandbox-dns | jq '.Reservations[].Instances[] | select((.State.Name=="running") and (.Tags[].Key=="Name") and (.Tags[].Value | startswith("linus-cluster"))) | .InstanceId'
  ```