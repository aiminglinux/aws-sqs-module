# Complete SQS Queue Example

Configuration in this directory creates:
- Queue using module default settings
- FIFO (first-in, first-out) queue
- Unencrypted queue (encryption disabled)
- Queue encrypted with customer managed KMS key
- Queue encrypted with default SQS SSE (server-side encryption) w/ separate dead-letter queue
  - Dead letter queue created in separate module definition
- Queue with dead-letter queue created in the same module defintion w/ queue policies for both the source queue and dead-letter queue
- Disabled queue (no resources created)

## Usage

To run this example you need to execute:

```bash
$ terraform init
$ terraform plan
$ terraform apply
```

Note that this example may create resources which cost money. Run `terraform destroy` when you don't need these resources.

<!-- BEGINNING OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
README.md updated successfully
<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->

<!-- BEGIN_TF_DOCS -->
## Requirements

| Name | Version |
|------|---------|
| <a name="requirement_terraform"></a> [terraform](#requirement_terraform) | >= 1.0 |
| <a name="requirement_aws"></a> [aws](#requirement_aws) | >= 4.36 |

## Providers

| Name | Version |
|------|---------|
| <a name="provider_aws"></a> [aws](#provider_aws) | 5.93.0 |

## Inputs

No inputs.

## Outputs

| Name | Description |
|------|-------------|
| <a name="output_cmk_encrypted_sqs_dlq_arn"></a> [cmk_encrypted_sqs_dlq_arn](#output_cmk_encrypted_sqs_dlq_arn) | The ARN of the SQS queue |
| <a name="output_cmk_encrypted_sqs_dlq_id"></a> [cmk_encrypted_sqs_dlq_id](#output_cmk_encrypted_sqs_dlq_id) | The URL for the created Amazon SQS queue |
| <a name="output_cmk_encrypted_sqs_dlq_name"></a> [cmk_encrypted_sqs_dlq_name](#output_cmk_encrypted_sqs_dlq_name) | The name of the SQS queue |
| <a name="output_cmk_encrypted_sqs_dlq_url"></a> [cmk_encrypted_sqs_dlq_url](#output_cmk_encrypted_sqs_dlq_url) | Same as `dead_letter_queue_id`: The URL for the created Amazon SQS queue |
| <a name="output_cmk_encrypted_sqs_queue_arn"></a> [cmk_encrypted_sqs_queue_arn](#output_cmk_encrypted_sqs_queue_arn) | The ARN of the SQS queue |
| <a name="output_cmk_encrypted_sqs_queue_id"></a> [cmk_encrypted_sqs_queue_id](#output_cmk_encrypted_sqs_queue_id) | The URL for the created Amazon SQS queue |
| <a name="output_cmk_encrypted_sqs_queue_name"></a> [cmk_encrypted_sqs_queue_name](#output_cmk_encrypted_sqs_queue_name) | The name of the SQS queue |
| <a name="output_cmk_encrypted_sqs_queue_url"></a> [cmk_encrypted_sqs_queue_url](#output_cmk_encrypted_sqs_queue_url) | Same as `queue_id`: The URL for the created Amazon SQS queue |
| <a name="output_default_sqs_dlq_arn"></a> [default_sqs_dlq_arn](#output_default_sqs_dlq_arn) | The ARN of the SQS queue |
| <a name="output_default_sqs_dlq_id"></a> [default_sqs_dlq_id](#output_default_sqs_dlq_id) | The URL for the created Amazon SQS queue |
| <a name="output_default_sqs_dlq_name"></a> [default_sqs_dlq_name](#output_default_sqs_dlq_name) | The name of the SQS queue |
| <a name="output_default_sqs_dlq_url"></a> [default_sqs_dlq_url](#output_default_sqs_dlq_url) | Same as `dead_letter_queue_id`: The URL for the created Amazon SQS queue |
| <a name="output_default_sqs_queue_arn"></a> [default_sqs_queue_arn](#output_default_sqs_queue_arn) | The ARN of the SQS queue |
| <a name="output_default_sqs_queue_id"></a> [default_sqs_queue_id](#output_default_sqs_queue_id) | The URL for the created Amazon SQS queue |
| <a name="output_default_sqs_queue_name"></a> [default_sqs_queue_name](#output_default_sqs_queue_name) | The name of the SQS queue |
| <a name="output_default_sqs_queue_url"></a> [default_sqs_queue_url](#output_default_sqs_queue_url) | Same as `queue_id`: The URL for the created Amazon SQS queue |
| <a name="output_disabled_sqs_dlq_arn"></a> [disabled_sqs_dlq_arn](#output_disabled_sqs_dlq_arn) | The ARN of the SQS queue |
| <a name="output_disabled_sqs_dlq_id"></a> [disabled_sqs_dlq_id](#output_disabled_sqs_dlq_id) | The URL for the created Amazon SQS queue |
| <a name="output_disabled_sqs_dlq_name"></a> [disabled_sqs_dlq_name](#output_disabled_sqs_dlq_name) | The name of the SQS queue |
| <a name="output_disabled_sqs_dlq_url"></a> [disabled_sqs_dlq_url](#output_disabled_sqs_dlq_url) | Same as `dead_letter_queue_id`: The URL for the created Amazon SQS queue |
| <a name="output_disabled_sqs_queue_arn"></a> [disabled_sqs_queue_arn](#output_disabled_sqs_queue_arn) | The ARN of the SQS queue |
| <a name="output_disabled_sqs_queue_id"></a> [disabled_sqs_queue_id](#output_disabled_sqs_queue_id) | The URL for the created Amazon SQS queue |
| <a name="output_disabled_sqs_queue_name"></a> [disabled_sqs_queue_name](#output_disabled_sqs_queue_name) | The name of the SQS queue |
| <a name="output_disabled_sqs_queue_url"></a> [disabled_sqs_queue_url](#output_disabled_sqs_queue_url) | Same as `queue_id`: The URL for the created Amazon SQS queue |
| <a name="output_fifo_sqs_dlq_arn"></a> [fifo_sqs_dlq_arn](#output_fifo_sqs_dlq_arn) | The ARN of the SQS queue |
| <a name="output_fifo_sqs_dlq_id"></a> [fifo_sqs_dlq_id](#output_fifo_sqs_dlq_id) | The URL for the created Amazon SQS queue |
| <a name="output_fifo_sqs_dlq_name"></a> [fifo_sqs_dlq_name](#output_fifo_sqs_dlq_name) | The name of the SQS queue |
| <a name="output_fifo_sqs_dlq_url"></a> [fifo_sqs_dlq_url](#output_fifo_sqs_dlq_url) | Same as `dead_letter_queue_id`: The URL for the created Amazon SQS queue |
| <a name="output_fifo_sqs_queue_arn"></a> [fifo_sqs_queue_arn](#output_fifo_sqs_queue_arn) | The ARN of the SQS queue |
| <a name="output_fifo_sqs_queue_id"></a> [fifo_sqs_queue_id](#output_fifo_sqs_queue_id) | The URL for the created Amazon SQS queue |
| <a name="output_fifo_sqs_queue_name"></a> [fifo_sqs_queue_name](#output_fifo_sqs_queue_name) | The name of the SQS queue |
| <a name="output_fifo_sqs_queue_url"></a> [fifo_sqs_queue_url](#output_fifo_sqs_queue_url) | Same as `queue_id`: The URL for the created Amazon SQS queue |
| <a name="output_sqs_with_dlq_dlq_arn"></a> [sqs_with_dlq_dlq_arn](#output_sqs_with_dlq_dlq_arn) | The ARN of the SQS queue |
| <a name="output_sqs_with_dlq_dlq_id"></a> [sqs_with_dlq_dlq_id](#output_sqs_with_dlq_dlq_id) | The URL for the created Amazon SQS queue |
| <a name="output_sqs_with_dlq_dlq_name"></a> [sqs_with_dlq_dlq_name](#output_sqs_with_dlq_dlq_name) | The name of the SQS queue |
| <a name="output_sqs_with_dlq_dlq_url"></a> [sqs_with_dlq_dlq_url](#output_sqs_with_dlq_dlq_url) | Same as `dead_letter_queue_id`: The URL for the created Amazon SQS queue |
| <a name="output_sqs_with_dlq_queue_arn"></a> [sqs_with_dlq_queue_arn](#output_sqs_with_dlq_queue_arn) | The ARN of the SQS queue |
| <a name="output_sqs_with_dlq_queue_id"></a> [sqs_with_dlq_queue_id](#output_sqs_with_dlq_queue_id) | The URL for the created Amazon SQS queue |
| <a name="output_sqs_with_dlq_queue_name"></a> [sqs_with_dlq_queue_name](#output_sqs_with_dlq_queue_name) | The name of the SQS queue |
| <a name="output_sqs_with_dlq_queue_url"></a> [sqs_with_dlq_queue_url](#output_sqs_with_dlq_queue_url) | Same as `queue_id`: The URL for the created Amazon SQS queue |
| <a name="output_sse_encrypted_dlq_sqs_dlq_arn"></a> [sse_encrypted_dlq_sqs_dlq_arn](#output_sse_encrypted_dlq_sqs_dlq_arn) | The ARN of the SQS queue |
| <a name="output_sse_encrypted_dlq_sqs_dlq_id"></a> [sse_encrypted_dlq_sqs_dlq_id](#output_sse_encrypted_dlq_sqs_dlq_id) | The URL for the created Amazon SQS queue |
| <a name="output_sse_encrypted_dlq_sqs_dlq_name"></a> [sse_encrypted_dlq_sqs_dlq_name](#output_sse_encrypted_dlq_sqs_dlq_name) | The name of the SQS queue |
| <a name="output_sse_encrypted_dlq_sqs_dlq_url"></a> [sse_encrypted_dlq_sqs_dlq_url](#output_sse_encrypted_dlq_sqs_dlq_url) | Same as `dead_letter_queue_id`: The URL for the created Amazon SQS queue |
| <a name="output_sse_encrypted_dlq_sqs_queue_arn"></a> [sse_encrypted_dlq_sqs_queue_arn](#output_sse_encrypted_dlq_sqs_queue_arn) | The ARN of the SQS queue |
| <a name="output_sse_encrypted_dlq_sqs_queue_id"></a> [sse_encrypted_dlq_sqs_queue_id](#output_sse_encrypted_dlq_sqs_queue_id) | The URL for the created Amazon SQS queue |
| <a name="output_sse_encrypted_dlq_sqs_queue_name"></a> [sse_encrypted_dlq_sqs_queue_name](#output_sse_encrypted_dlq_sqs_queue_name) | The name of the SQS queue |
| <a name="output_sse_encrypted_dlq_sqs_queue_url"></a> [sse_encrypted_dlq_sqs_queue_url](#output_sse_encrypted_dlq_sqs_queue_url) | Same as `queue_id`: The URL for the created Amazon SQS queue |
| <a name="output_sse_encrypted_sqs_dlq_arn"></a> [sse_encrypted_sqs_dlq_arn](#output_sse_encrypted_sqs_dlq_arn) | The ARN of the SQS queue |
| <a name="output_sse_encrypted_sqs_dlq_id"></a> [sse_encrypted_sqs_dlq_id](#output_sse_encrypted_sqs_dlq_id) | The URL for the created Amazon SQS queue |
| <a name="output_sse_encrypted_sqs_dlq_name"></a> [sse_encrypted_sqs_dlq_name](#output_sse_encrypted_sqs_dlq_name) | The name of the SQS queue |
| <a name="output_sse_encrypted_sqs_dlq_url"></a> [sse_encrypted_sqs_dlq_url](#output_sse_encrypted_sqs_dlq_url) | Same as `dead_letter_queue_id`: The URL for the created Amazon SQS queue |
| <a name="output_sse_encrypted_sqs_queue_arn"></a> [sse_encrypted_sqs_queue_arn](#output_sse_encrypted_sqs_queue_arn) | The ARN of the SQS queue |
| <a name="output_sse_encrypted_sqs_queue_id"></a> [sse_encrypted_sqs_queue_id](#output_sse_encrypted_sqs_queue_id) | The URL for the created Amazon SQS queue |
| <a name="output_sse_encrypted_sqs_queue_name"></a> [sse_encrypted_sqs_queue_name](#output_sse_encrypted_sqs_queue_name) | The name of the SQS queue |
| <a name="output_sse_encrypted_sqs_queue_url"></a> [sse_encrypted_sqs_queue_url](#output_sse_encrypted_sqs_queue_url) | Same as `queue_id`: The URL for the created Amazon SQS queue |
| <a name="output_unencrypted_sqs_dlq_arn"></a> [unencrypted_sqs_dlq_arn](#output_unencrypted_sqs_dlq_arn) | The ARN of the SQS queue |
| <a name="output_unencrypted_sqs_dlq_id"></a> [unencrypted_sqs_dlq_id](#output_unencrypted_sqs_dlq_id) | The URL for the created Amazon SQS queue |
| <a name="output_unencrypted_sqs_dlq_name"></a> [unencrypted_sqs_dlq_name](#output_unencrypted_sqs_dlq_name) | The name of the SQS queue |
| <a name="output_unencrypted_sqs_dlq_url"></a> [unencrypted_sqs_dlq_url](#output_unencrypted_sqs_dlq_url) | Same as `dead_letter_queue_id`: The URL for the created Amazon SQS queue |
| <a name="output_unencrypted_sqs_queue_arn"></a> [unencrypted_sqs_queue_arn](#output_unencrypted_sqs_queue_arn) | The ARN of the SQS queue |
| <a name="output_unencrypted_sqs_queue_id"></a> [unencrypted_sqs_queue_id](#output_unencrypted_sqs_queue_id) | The URL for the created Amazon SQS queue |
| <a name="output_unencrypted_sqs_queue_name"></a> [unencrypted_sqs_queue_name](#output_unencrypted_sqs_queue_name) | The name of the SQS queue |
| <a name="output_unencrypted_sqs_queue_url"></a> [unencrypted_sqs_queue_url](#output_unencrypted_sqs_queue_url) | Same as `queue_id`: The URL for the created Amazon SQS queue |
<!-- END_TF_DOCS -->
