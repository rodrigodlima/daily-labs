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
