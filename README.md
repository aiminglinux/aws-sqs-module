# my-sqs-module

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

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_content_based_deduplication"></a> [content_based_deduplication](#input_content_based_deduplication) | Enables content-based deduplication for FIFO queues | `bool` | `null` | no |
| <a name="input_create"></a> [create](#input_create) | Whether to create SQS queue | `bool` | `true` | no |
| <a name="input_create_dlq"></a> [create_dlq](#input_create_dlq) | Determines whether to create SQS dead letter queue | `bool` | `false` | no |
| <a name="input_create_dlq_queue_policy"></a> [create_dlq_queue_policy](#input_create_dlq_queue_policy) | Whether to create SQS queue policy | `bool` | `false` | no |
| <a name="input_create_queue_policy"></a> [create_queue_policy](#input_create_queue_policy) | Whether to create SQS queue policy | `bool` | `false` | no |
| <a name="input_deduplication_scope"></a> [deduplication_scope](#input_deduplication_scope) | Specifies whether message deduplication occurs at the message group or queue level | `string` | `null` | no |
| <a name="input_delay_seconds"></a> [delay_seconds](#input_delay_seconds) | The time in seconds that the delivery of all messages in the queue will be delayed. An integer from 0 to 900 (15 minutes) | `number` | `null` | no |
| <a name="input_dlq_content_based_deduplication"></a> [dlq_content_based_deduplication](#input_dlq_content_based_deduplication) | Enables content-based deduplication for FIFO queues | `bool` | `null` | no |
| <a name="input_dlq_deduplication_scope"></a> [dlq_deduplication_scope](#input_dlq_deduplication_scope) | Specifies whether message deduplication occurs at the message group or queue level | `string` | `null` | no |
| <a name="input_dlq_delay_seconds"></a> [dlq_delay_seconds](#input_dlq_delay_seconds) | The time in seconds that the delivery of all messages in the queue will be delayed. An integer from 0 to 900 (15 minutes) | `number` | `null` | no |
| <a name="input_dlq_kms_data_key_reuse_period_seconds"></a> [dlq_kms_data_key_reuse_period_seconds](#input_dlq_kms_data_key_reuse_period_seconds) | The length of time, in seconds, for which Amazon SQS can reuse a data key to encrypt or decrypt messages before calling AWS KMS again. An integer representing seconds, between 60 seconds (1 minute) and 86,400 seconds (24 hours) | `number` | `null` | no |
| <a name="input_dlq_kms_master_key_id"></a> [dlq_kms_master_key_id](#input_dlq_kms_master_key_id) | The ID of an AWS-managed customer master key (CMK) for Amazon SQS or a custom CMK | `string` | `null` | no |
| <a name="input_dlq_message_retention_seconds"></a> [dlq_message_retention_seconds](#input_dlq_message_retention_seconds) | The number of seconds Amazon SQS retains a message. Integer representing seconds, from 60 (1 minute) to 1209600 (14 days) | `number` | `null` | no |
| <a name="input_dlq_name"></a> [dlq_name](#input_dlq_name) | This is the human-readable name of the queue. If omitted, Terraform will assign a random name | `string` | `null` | no |
| <a name="input_dlq_queue_policy_statements"></a> [dlq_queue_policy_statements](#input_dlq_queue_policy_statements) | A map of IAM policy [statements](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/iam_policy_document#statement) for custom permission usage | `any` | `{}` | no |
| <a name="input_dlq_receive_wait_time_seconds"></a> [dlq_receive_wait_time_seconds](#input_dlq_receive_wait_time_seconds) | The time for which a ReceiveMessage call will wait for a message to arrive (long polling) before returning. An integer from 0 to 20 (seconds) | `number` | `null` | no |
| <a name="input_dlq_redrive_allow_policy"></a> [dlq_redrive_allow_policy](#input_dlq_redrive_allow_policy) | The JSON policy to set up the Dead Letter Queue redrive permission, see AWS docs. | `any` | `{}` | no |
| <a name="input_dlq_sqs_managed_sse_enabled"></a> [dlq_sqs_managed_sse_enabled](#input_dlq_sqs_managed_sse_enabled) | Boolean to enable server-side encryption (SSE) of message content with SQS-owned encryption keys | `bool` | `true` | no |
| <a name="input_dlq_tags"></a> [dlq_tags](#input_dlq_tags) | A mapping of additional tags to assign to the dead letter queue | `map(string)` | `{}` | no |
| <a name="input_dlq_visibility_timeout_seconds"></a> [dlq_visibility_timeout_seconds](#input_dlq_visibility_timeout_seconds) | The visibility timeout for the queue. An integer from 0 to 43200 (12 hours) | `number` | `null` | no |
| <a name="input_fifo_queue"></a> [fifo_queue](#input_fifo_queue) | Boolean designating a FIFO queue | `bool` | `false` | no |
| <a name="input_fifo_throughput_limit"></a> [fifo_throughput_limit](#input_fifo_throughput_limit) | Specifies whether the FIFO queue throughput quota applies to the entire queue or per message group | `string` | `null` | no |
| <a name="input_kms_data_key_reuse_period_seconds"></a> [kms_data_key_reuse_period_seconds](#input_kms_data_key_reuse_period_seconds) | The length of time, in seconds, for which Amazon SQS can reuse a data key to encrypt or decrypt messages before calling AWS KMS again. An integer representing seconds, between 60 seconds (1 minute) and 86,400 seconds (24 hours) | `number` | `null` | no |
| <a name="input_kms_master_key_id"></a> [kms_master_key_id](#input_kms_master_key_id) | The ID of an AWS-managed customer master key (CMK) for Amazon SQS or a custom CMK | `string` | `null` | no |
| <a name="input_max_message_size"></a> [max_message_size](#input_max_message_size) | The limit of how many bytes a message can contain before Amazon SQS rejects it. An integer from 1024 bytes (1 KiB) up to 262144 bytes (256 KiB) | `number` | `null` | no |
| <a name="input_message_retention_seconds"></a> [message_retention_seconds](#input_message_retention_seconds) | The number of seconds Amazon SQS retains a message. Integer representing seconds, from 60 (1 minute) to 1209600 (14 days) | `number` | `null` | no |
| <a name="input_name"></a> [name](#input_name) | This is the human-readable name of the queue. If omitted, Terraform will assign a random name | `string` | `null` | no |
| <a name="input_override_dlq_queue_policy_documents"></a> [override_dlq_queue_policy_documents](#input_override_dlq_queue_policy_documents) | List of IAM policy documents that are merged together into the exported document. In merging, statements with non-blank `sid`s will override statements with the same `sid` | `list(string)` | `[]` | no |
| <a name="input_override_queue_policy_documents"></a> [override_queue_policy_documents](#input_override_queue_policy_documents) | List of IAM policy documents that are merged together into the exported document. In merging, statements with non-blank `sid`s will override statements with the same `sid` | `list(string)` | `[]` | no |
| <a name="input_queue_policy_statements"></a> [queue_policy_statements](#input_queue_policy_statements) | A map of IAM policy [statements](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/iam_policy_document#statement) for custom permission usage | `any` | `{}` | no |
| <a name="input_receive_wait_time_seconds"></a> [receive_wait_time_seconds](#input_receive_wait_time_seconds) | The time for which a ReceiveMessage call will wait for a message to arrive (long polling) before returning. An integer from 0 to 20 (seconds) | `number` | `null` | no |
| <a name="input_redrive_allow_policy"></a> [redrive_allow_policy](#input_redrive_allow_policy) | The JSON policy to set up the Dead Letter Queue redrive permission, see AWS docs. | `any` | `{}` | no |
| <a name="input_redrive_policy"></a> [redrive_policy](#input_redrive_policy) | The JSON policy to set up the Dead Letter Queue, see AWS docs. Note: when specifying maxReceiveCount, you must specify it as an integer (5), and not a string ("5") | `any` | `{}` | no |
| <a name="input_source_dlq_queue_policy_documents"></a> [source_dlq_queue_policy_documents](#input_source_dlq_queue_policy_documents) | List of IAM policy documents that are merged together into the exported document. Statements must have unique `sid`s | `list(string)` | `[]` | no |
| <a name="input_source_queue_policy_documents"></a> [source_queue_policy_documents](#input_source_queue_policy_documents) | List of IAM policy documents that are merged together into the exported document. Statements must have unique `sid`s | `list(string)` | `[]` | no |
| <a name="input_sqs_managed_sse_enabled"></a> [sqs_managed_sse_enabled](#input_sqs_managed_sse_enabled) | Boolean to enable server-side encryption (SSE) of message content with SQS-owned encryption keys | `bool` | `true` | no |
| <a name="input_tags"></a> [tags](#input_tags) | A mapping of tags to assign to all resources | `map(string)` | `{}` | no |
| <a name="input_use_name_prefix"></a> [use_name_prefix](#input_use_name_prefix) | Determines whether `name` is used as a prefix | `bool` | `false` | no |
| <a name="input_visibility_timeout_seconds"></a> [visibility_timeout_seconds](#input_visibility_timeout_seconds) | The visibility timeout for the queue. An integer from 0 to 43200 (12 hours) | `number` | `null` | no |

## Outputs

| Name | Description |
|------|-------------|
| <a name="output_dead_letter_queue_arn"></a> [dead_letter_queue_arn](#output_dead_letter_queue_arn) | The ARN of the SQS queue |
| <a name="output_dead_letter_queue_id"></a> [dead_letter_queue_id](#output_dead_letter_queue_id) | The URL for the created Amazon SQS queue |
| <a name="output_dead_letter_queue_name"></a> [dead_letter_queue_name](#output_dead_letter_queue_name) | The name of the SQS queue |
| <a name="output_dead_letter_queue_url"></a> [dead_letter_queue_url](#output_dead_letter_queue_url) | Same as `dead_letter_queue_id`: The URL for the created Amazon SQS queue |
| <a name="output_queue_arn"></a> [queue_arn](#output_queue_arn) | The ARN of the SQS queue |
| <a name="output_queue_id"></a> [queue_id](#output_queue_id) | The URL for the created Amazon SQS queue |
| <a name="output_queue_name"></a> [queue_name](#output_queue_name) | The name of the SQS queue |
| <a name="output_queue_url"></a> [queue_url](#output_queue_url) | Same as `queue_id`: The URL for the created Amazon SQS queue |
<!-- END_TF_DOCS -->