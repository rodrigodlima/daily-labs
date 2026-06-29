# Terraform notes

Short, practical notes collected while studying and testing.

## Format recursively

```bash
terraform fmt -recursive
```

## Show a single resource from state

```bash
terraform state show aws_instance.web
```

## Import existing resource (block)

```hcl
import {
  to = aws_s3_bucket.logs
  id = "my-logs-bucket"
}
```
