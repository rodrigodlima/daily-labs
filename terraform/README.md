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

## Target a single resource (use sparingly)

```bash
terraform plan -target=module.vpc
```

## Moved block for refactors

```hcl
moved {
  from = aws_instance.web
  to   = module.web.aws_instance.this
}
```

## Validate and lint

```bash
terraform validate && tflint
```

## Workspaces

```bash
terraform workspace new staging && terraform workspace select staging
```

## Lifecycle prevent_destroy

```hcl
lifecycle {
  prevent_destroy = true
}
```

## Output sensitive value

```bash
terraform output -raw db_password
```

## Graph dependencies

```bash
terraform graph | dot -Tsvg > graph.svg
```

## Check provider versions

```bash
terraform version && terraform providers
```

## for_each over a map

```hcl
resource "aws_s3_bucket" "b" {
  for_each = var.buckets
  bucket   = each.value
}
```
