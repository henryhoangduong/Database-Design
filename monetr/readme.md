## Table `accounts`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `account_id` | `varchar` | Primary |
| `timezone` | `varchar` |  |
| `locale` | `varchar` |  |
| `stripe_customer_id` | `varchar` |  Nullable Unique |
| `stripe_subscription_id` | `varchar` |  Nullable Unique |
| `subscription_active_until` | `timestamp` |  Nullable |
| `stripe_webhook_latest_timestamp` | `timestamp` |  Nullable |
| `subscription_status` | `varchar` |  Nullable |
| `trial_ends_at` | `timestamp` |  Nullable |
| `created_at` | `timestamp` |  |
| `trial_expiry_notification_sent_at` | `timestamp` |  Nullable |

## Table `bank_accounts`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `bank_account_id` | `varchar` | Primary |
| `account_id` | `varchar` | Primary |
| `link_id` | `varchar` |  |
| `plaid_bank_account_id` | `varchar` |  Nullable |
| `name` | `varchar` |  |
| `original_name` | `varchar` |  Nullable |
| `mask` | `varchar` |  Nullable |
| `account_type` | `varchar` |  Nullable |
| `account_sub_type` | `varchar` |  Nullable |
| `status` | `varchar` |  |
| `available_balance` | `int8` |  |
| `current_balance` | `int8` |  |
| `last_updated` | `timestamp` |  |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `limit_balance` | `int8` |  |
| `currency` | `text` |  |
| `deleted_at` | `timestamp` |  Nullable |
| `lunch_flow_bank_account_id` | `varchar` |  Nullable Unique |

## Table `betas`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `beta_id` | `varchar` | Primary |
| `code_hash` | `text` |  Unique |
| `used_by` | `varchar` |  Nullable |
| `expires_at` | `timestamp` |  |

## Table `cron_jobs`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `queue` | `text` | Primary |
| `cron_schedule` | `text` |  |
| `last_run_at` | `timestamp` |  Nullable |
| `next_run_at` | `timestamp` |  |

## Table `files`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `file_id` | `varchar` | Primary |
| `account_id` | `varchar` | Primary |
| `content_type` | `varchar` |  |
| `name` | `varchar` |  |
| `size` | `int4` |  |
| `created_at` | `timestamp` |  |
| `created_by` | `varchar` |  |
| `deleted_at` | `timestamp` |  Nullable |
| `reconciled_at` | `timestamp` |  Nullable |
| `expires_at` | `timestamp` |  Nullable |
| `kind` | `text` |  |

## Table `funding_schedules`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `funding_schedule_id` | `varchar` | Primary |
| `account_id` | `varchar` | Primary |
| `bank_account_id` | `varchar` | Primary |
| `name` | `varchar` |  |
| `description` | `varchar` |  Nullable |
| `ruleset` | `text` |  |
| `last_recurrence` | `timestamp` |  Nullable |
| `next_recurrence` | `timestamp` |  |
| `next_recurrence_original` | `timestamp` |  |
| `exclude_weekends` | `bool` |  |
| `wait_for_deposit` | `bool` |  |
| `estimated_deposit` | `int8` |  Nullable |
| `auto_create_transaction` | `bool` |  |

## Table `gopg_migrations`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `int4` |  |
| `version` | `int8` |  Nullable |
| `created_at` | `timestamptz` |  Nullable |

## Table `jobs`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `job_id` | `varchar` | Primary |
| `queue` | `varchar` |  |
| `signature` | `varchar` |  |
| `status` | `varchar` |  |
| `input` | `jsonb` |  Nullable |
| `output` | `jsonb` |  Nullable |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `started_at` | `timestamp` |  Nullable |
| `completed_at` | `timestamp` |  Nullable |
| `sentry_trace_id` | `text` |  Nullable |
| `priority` | `int8` |  |
| `sentry_baggage` | `text` |  Nullable |
| `attempt` | `int4` |  |

## Table `links`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `link_id` | `varchar` | Primary |
| `account_id` | `varchar` | Primary |
| `plaid_link_id` | `varchar` |  Nullable |
| `institution_name` | `varchar` |  Nullable |
| `description` | `varchar` |  Nullable |
| `created_at` | `timestamp` |  |
| `created_by` | `varchar` |  |
| `updated_at` | `timestamp` |  |
| `deleted_at` | `timestamp` |  Nullable |
| `lunch_flow_link_id` | `varchar` |  Nullable Unique |
| `link_type` | `text` |  |

## Table `logins`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `login_id` | `varchar` | Primary |
| `email` | `varchar` |  Unique |
| `first_name` | `varchar` |  Nullable |
| `last_name` | `varchar` |  Nullable |
| `totp` | `text` |  Nullable |
| `totp_enabled_at` | `timestamp` |  Nullable |
| `crypt` | `bytea` |  |
| `is_enabled` | `bool` |  |
| `is_email_verified` | `bool` |  |
| `email_verified_at` | `timestamp` |  Nullable |
| `password_reset_at` | `timestamp` |  Nullable |
| `totp_recovery_codes` | `_text` |  Nullable |

## Table `lunch_flow_bank_accounts`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `lunch_flow_bank_account_id` | `varchar` | Primary |
| `lunch_flow_link_id` | `varchar` |  |
| `account_id` | `varchar` | Primary |
| `lunch_flow_id` | `text` |  |
| `lunch_flow_status` | `text` |  |
| `name` | `text` |  |
| `institution_name` | `text` |  |
| `provider` | `text` |  |
| `currency` | `text` |  |
| `status` | `text` |  |
| `current_balance` | `int8` |  |
| `created_by` | `varchar` |  |
| `updated_at` | `timestamp` |  |
| `created_at` | `timestamp` |  |
| `deleted_at` | `timestamp` |  Nullable |

## Table `lunch_flow_links`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `lunch_flow_link_id` | `varchar` | Primary |
| `account_id` | `varchar` | Primary |
| `secret_id` | `varchar` |  |
| `name` | `text` |  |
| `api_url` | `text` |  |
| `status` | `text` |  |
| `last_manual_sync` | `timestamp` |  Nullable |
| `last_successful_update` | `timestamp` |  Nullable |
| `last_attempted_update` | `timestamp` |  Nullable |
| `created_by` | `varchar` |  |
| `updated_at` | `timestamp` |  |
| `created_at` | `timestamp` |  |
| `deleted_at` | `timestamp` |  Nullable |

## Table `lunch_flow_transactions`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `lunch_flow_transaction_id` | `varchar` | Primary |
| `account_id` | `varchar` | Primary |
| `lunch_flow_bank_account_id` | `varchar` |  |
| `lunch_flow_id` | `text` |  |
| `merchant` | `text` |  |
| `description` | `text` |  |
| `currency` | `text` |  |
| `amount` | `int8` |  |
| `is_pending` | `bool` |  |
| `date` | `timestamp` |  |
| `created_at` | `timestamp` |  |
| `deleted_at` | `timestamp` |  Nullable |

## Table `plaid_bank_accounts`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `plaid_bank_account_id` | `varchar` | Primary |
| `account_id` | `varchar` | Primary |
| `plaid_link_id` | `varchar` |  |
| `plaid_id` | `text` |  |
| `name` | `varchar` |  |
| `official_name` | `varchar` |  Nullable |
| `mask` | `varchar` |  Nullable |
| `available_balance` | `int8` |  |
| `current_balance` | `int8` |  |
| `limit_balance` | `int8` |  |
| `created_at` | `timestamp` |  |
| `created_by` | `varchar` |  |
| `currency` | `text` |  |

## Table `plaid_links`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `plaid_link_id` | `varchar` | Primary |
| `account_id` | `varchar` | Primary |
| `secret_id` | `varchar` |  |
| `item_id` | `text` |  Unique |
| `products` | `_text` |  |
| `error_code` | `text` |  Nullable |
| `expiration_date` | `timestamp` |  Nullable |
| `new_accounts_available` | `bool` |  |
| `webhook_url` | `text` |  Nullable |
| `institution_id` | `text` |  |
| `institution_name` | `text` |  |
| `last_manual_sync` | `timestamp` |  Nullable |
| `last_successful_update` | `timestamp` |  Nullable |
| `last_attempted_update` | `timestamp` |  Nullable |
| `updated_at` | `timestamp` |  |
| `created_at` | `timestamp` |  |
| `created_by` | `varchar` |  |
| `deleted_at` | `timestamp` |  Nullable |
| `last_account_sync` | `timestamp` |  Nullable |
| `status` | `text` |  |

## Table `plaid_syncs`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `plaid_sync_id` | `varchar` | Primary |
| `account_id` | `varchar` | Primary |
| `plaid_link_id` | `varchar` |  |
| `timestamp` | `timestamp` |  |
| `trigger` | `varchar` |  |
| `cursor` | `varchar` |  |
| `added` | `int4` |  |
| `modified` | `int4` |  |
| `removed` | `int4` |  |

## Table `plaid_transactions`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `plaid_transaction_id` | `varchar` | Primary |
| `account_id` | `varchar` | Primary |
| `plaid_bank_account_id` | `varchar` |  |
| `plaid_id` | `text` |  |
| `pending_plaid_id` | `text` |  Nullable |
| `categories` | `_text` |  Nullable |
| `date` | `timestamp` |  |
| `authorized_date` | `timestamp` |  Nullable |
| `name` | `text` |  |
| `merchant_name` | `text` |  Nullable |
| `amount` | `int8` |  |
| `currency` | `varchar` |  |
| `is_pending` | `bool` |  |
| `created_at` | `timestamp` |  |
| `deleted_at` | `timestamp` |  Nullable |
| `category` | `text` |  Nullable |

## Table `secrets`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `secret_id` | `varchar` | Primary |
| `account_id` | `varchar` | Primary |
| `kind` | `varchar` |  |
| `key_id` | `text` |  Nullable |
| `version` | `text` |  Nullable |
| `secret` | `text` |  |
| `updated_at` | `timestamp` |  |
| `created_at` | `timestamp` |  |

## Table `settings`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `account_id` | `int8` | Primary |
| `max_safe_to_spend` | `jsonb` |  |

## Table `spending`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `spending_id` | `varchar` | Primary |
| `account_id` | `varchar` | Primary |
| `bank_account_id` | `varchar` | Primary |
| `funding_schedule_id` | `varchar` |  |
| `spending_type` | `int2` |  |
| `name` | `varchar` |  |
| `description` | `varchar` |  Nullable |
| `ruleset` | `text` |  Nullable |
| `target_amount` | `int8` |  |
| `current_amount` | `int8` |  |
| `used_amount` | `int8` |  |
| `last_recurrence` | `timestamp` |  Nullable |
| `next_recurrence` | `timestamp` |  |
| `last_spent_from` | `timestamp` |  Nullable |
| `next_contribution_amount` | `int8` |  |
| `is_behind` | `bool` |  |
| `is_paused` | `bool` |  |
| `created_at` | `timestamp` |  |
| `auto_create_transaction` | `bool` |  |

## Table `transaction_clusters`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `transaction_cluster_id` | `varchar` | Primary |
| `account_id` | `varchar` | Primary |
| `bank_account_id` | `varchar` |  |
| `name` | `text` |  |
| `members` | `_varchar` |  |
| `created_at` | `timestamp` |  |
| `signature` | `text` |  Nullable |
| `debug` | `jsonb` |  Nullable |
| `merchant` | `jsonb` |  Nullable |
| `centroid` | `varchar` |  Nullable |
| `original_name` | `text` |  |
| `updated_at` | `timestamp` |  |

## Table `transaction_import_mappings`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `transaction_import_mapping_id` | `varchar` | Primary |
| `account_id` | `varchar` | Primary |
| `signature` | `text` |  |
| `mapping` | `jsonb` |  |
| `created_by` | `varchar` |  |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |

## Table `transaction_imports`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `transaction_import_id` | `varchar` | Primary |
| `account_id` | `varchar` | Primary |
| `bank_account_id` | `varchar` | Primary |
| `file_id` | `varchar` |  |
| `transaction_import_mapping_id` | `varchar` |  Nullable |
| `delimeter` | `varchar` |  |
| `headers` | `_text` |  |
| `status` | `text` |  |
| `created_by` | `varchar` |  |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `completed_at` | `timestamp` |  Nullable |

## Table `transaction_uploads`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `transaction_upload_id` | `varchar` | Primary |
| `account_id` | `varchar` | Primary |
| `bank_account_id` | `varchar` | Primary |
| `file_id` | `varchar` |  |
| `status` | `varchar` |  |
| `error` | `text` |  Nullable |
| `created_at` | `timestamp` |  |
| `created_by` | `varchar` |  |
| `processed_at` | `timestamp` |  Nullable |
| `completed_at` | `timestamp` |  Nullable |

## Table `transactions`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `transaction_id` | `varchar` | Primary |
| `account_id` | `varchar` | Primary |
| `bank_account_id` | `varchar` | Primary |
| `spending_id` | `varchar` |  Nullable |
| `plaid_transaction_id` | `varchar` |  Nullable |
| `pending_plaid_transaction_id` | `varchar` |  Nullable |
| `name` | `text` |  Nullable |
| `original_name` | `text` |  |
| `merchant_name` | `text` |  Nullable |
| `original_merchant_name` | `text` |  Nullable |
| `categories` | `_text` |  Nullable |
| `amount` | `int8` |  |
| `spending_amount` | `int8` |  Nullable |
| `is_pending` | `bool` |  |
| `date` | `timestamp` |  |
| `created_at` | `timestamp` |  |
| `deleted_at` | `timestamp` |  Nullable |
| `category` | `text` |  Nullable |
| `upload_identifier` | `varchar` |  Nullable |
| `source` | `text` |  |
| `lunch_flow_transaction_id` | `varchar` |  Nullable Unique |
| `created_by_spending_id` | `varchar` |  Nullable |
| `created_by_funding_schedule_id` | `varchar` |  Nullable |

## Table `users`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `user_id` | `varchar` | Primary |
| `login_id` | `varchar` |  |
| `account_id` | `varchar` |  |
| `role` | `user_role` |  |

