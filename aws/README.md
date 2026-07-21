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
