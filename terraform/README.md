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
