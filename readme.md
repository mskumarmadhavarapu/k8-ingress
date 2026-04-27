Install OIDC provider
```
eksctl utils associate-iam-oidc-provider \
    --region us-east-1 \
    --cluster roboshop \
    --approve
```

Create IAM Policy
```
curl -o iam-policy.json https://raw.githubusercontent.com/kubernetes-sigs/aws-load-balancer-controller/v3.2.1/docs/install/iam_policy.json

aws iam create-policy \
    --policy-name AWSLoadBalancerControllerIAMPolicy \
    --policy-document file://iam-policy.json
```