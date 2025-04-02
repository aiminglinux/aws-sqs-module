# Terraform my-sqs-module Module

AWS SQS Queue Module

## Usage

```hcl
module "my_sqs_module" {
  source = "git::https://example.com/path/to/module.git?ref=v1.0.0"

  name = "example"
  tags = {
    Environment = "dev"
    Project     = "MyProject"
  }
}
```

<!-- BEGIN_TF_DOCS -->
<!-- END_TF_DOCS -->

## License

Copyright © 2025 Thao Le

Licensed under the [MIT License](LICENSE).