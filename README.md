# scp-examples
A collection of AWS Service Control Policies (SCP)

- [BlockAllbyAccount.json](BlockAllByAccount.json) - This SCP denies all actions in the set of accounts listed. This can deny a set of permissions in a set of accounts.
- [DenyAllOutsideUS.json](DenyAllOutsideUS.json) - This SCP denies all activities outside the us-east-1 region. Note that IAM, Logs and CloudWatch are still allowed, as these are necessary so that Lambda@Edge (among other things) will work correctly.
- [DenyEC2ExceptForCloud9.json](DenyEC2ExceptForCloud9.json) - This SCP allows you to deny running any EC2 except for EC2 that is running for Cloud9.
- [DenyEC2WithPublicIP.json](DenyEC2WithPublicIP.json) - This SCP allows you to prevent the running of an EC2 instance in a public subnet. The ARN on line 11 should refer to the ARN of a subnet (or subnets) that are public.
- [DenyOpenLambdaFunctionUrl.json](DenyOpenLambdaFunctionUrl.json) - This SCP allows you to deny creating a Lambda function URL with an AuthType of "None". In other words, you are prevented from creating a Lambda function URL that is public.
- [PreventS3CDExceptViaCFN.json](PreventS3CDExceptViaCFN.json) - This SCP prevents all users from creating or deleting a bucket except via CloudFormation. You could easily extend this SCP to add additional permissions that you don't want to be performed except via CloudFormation.
- [Quarantine.json](Quarantine.json) - This SCP can be used to quarantine an account. This SCP prevents any action within the account except for actions that are coming from the role ARN listed on line 11. This allows the admin to make changes to the account, while denying everything else.
