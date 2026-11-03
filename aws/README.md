# AWS notes

Short, practical notes collected while studying and testing.

## Who am I

```bash
aws sts get-caller-identity
```

## List S3 buckets with sizes

```bash
aws s3 ls s3://<bucket> --recursive --summarize --human-readable | tail -2
```

## Get latest Amazon Linux AMI via SSM

```bash
aws ssm get-parameters --names /aws/service/ami-amazon-linux-latest/al2023-ami-kernel-default-x86_64 --query 'Parameters[0].Value' --output text
```

## Tail CloudWatch logs

```bash
aws logs tail /aws/lambda/<fn> --follow
```

## Start SSM session instead of SSH

```bash
aws ssm start-session --target i-0123456789abcdef0
```

## Query with JMESPath

```bash
aws ec2 describe-instances --query 'Reservations[].Instances[].[InstanceId,State.Name]' --output table
```

## Presigned S3 URL

```bash
aws s3 presign s3://<bucket>/file.zip --expires-in 3600
```

## Assume role

```bash
aws sts assume-role --role-arn arn:aws:iam::<acct>:role/<role> --role-session-name me
```

## Find untagged EC2 instances

```bash
aws ec2 describe-instances --query 'Reservations[].Instances[?!not_null(Tags[?Key==`Owner`])].InstanceId' --output text
```

## List regions

```bash
aws ec2 describe-regions --query 'Regions[].RegionName' --output text
```
