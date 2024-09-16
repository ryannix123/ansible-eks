
# ansible-eks
Ansible Playbook to deploy a small EKS Kubernetes cluster using eksctl

To delete the cluster, run `eksctl delete cluster --name minimal-eks-cluster --region us-west-2`

You'll need several permissions to provision a basic Amazon EKS (Elastic Kubernetes Service) cluster in AWS. Here's a concise overview of the key permissions required:

EKS-specific permissions:

    eks:CreateCluster
    eks:DescribeCluster
    eks:ListClusters
    IAM permissions:

    iam:CreateRole
    iam:AttachRolePolicy
    iam:PutRolePolicy
    EC2 permissions:

    ec2:CreateSecurityGroup
    ec2:AuthorizeSecurityGroupIngress
    ec2:CreateVpc (if not using an existing VPC)
    ec2:CreateSubnet (if creating new subnets)

CloudFormation permissions (EKS uses CloudFormation to provision some resources):

    cloudformation:CreateStack
    cloudformation:DescribeStacks

Additional permissions for networking and logging:

    ec2:DescribeSubnets
    ec2:DescribeVpcs
    logs:CreateLogGroup
    logs:PutRetentionPolicy

*These permissions are typically bundled into an IAM policy. For simplicity, you could use the AWS-managed policy "AmazonEKSClusterPolicy", but for production environments, creating a custom policy with least-privilege principles is always recommended.*
