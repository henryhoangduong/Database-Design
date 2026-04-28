## Table `account_credits`

### Columns

| Name            | Type          | Constraints |
| --------------- | ------------- | ----------- |
| `id`            | `uuid`        | Primary     |
| `account_id`    | `uuid`        |             |
| `campaign_id`   | `uuid`        | Nullable    |
| `title`         | `varchar`     |             |
| `amount`        | `int4`        |             |
| `used`          | `int4`        |             |
| `granted_at`    | `timestamptz` |             |
| `expires_at`    | `timestamptz` | Nullable    |
| `revoked_at`    | `timestamptz` | Nullable    |
| `notes`         | `text`        | Nullable    |
| `user_metadata` | `jsonb`       |             |
| `created_at`    | `timestamptz` |             |
| `modified_at`   | `timestamptz` | Nullable    |
| `deleted_at`    | `timestamptz` | Nullable    |

## Table `accounts`

### Columns

| Name                        | Type          | Constraints |
| --------------------------- | ------------- | ----------- |
| `account_type`              | `varchar`     |             |
| `admin_id`                  | `uuid`        |             |
| `stripe_id`                 | `varchar`     | Nullable    |
| `open_collective_slug`      | `varchar`     | Nullable    |
| `email`                     | `varchar`     | Nullable    |
| `country`                   | `varchar`     |             |
| `currency`                  | `varchar`     |             |
| `is_details_submitted`      | `bool`        |             |
| `is_charges_enabled`        | `bool`        |             |
| `is_payouts_enabled`        | `bool`        |             |
| `processor_fees_applicable` | `bool`        |             |
| `platform_fee_percent`      | `int4`        | Nullable    |
| `business_type`             | `varchar`     | Nullable    |
| `status`                    | `varchar`     |             |
| `next_review_threshold`     | `int4`        | Nullable    |
| `data`                      | `jsonb`       |             |
| `id`                        | `uuid`        | Primary     |
| `created_at`                | `timestamptz` |             |
| `modified_at`               | `timestamptz` | Nullable    |
| `deleted_at`                | `timestamptz` | Nullable    |
| `platform_fee_fixed`        | `int4`        | Nullable    |
| `campaign_id`               | `uuid`        | Nullable    |
| `billing_name`              | `varchar`     | Nullable    |
| `billing_address`           | `jsonb`       | Nullable    |
| `billing_additional_info`   | `text`        | Nullable    |
| `billing_notes`             | `text`        | Nullable    |
| `credit_balance`            | `int4`        |             |

## Table `alembic_version`

### Columns

| Name          | Type      | Constraints |
| ------------- | --------- | ----------- |
| `version_num` | `varchar` | Primary     |

## Table `benefit_grants`

### Columns

| Name              | Type          | Constraints |
| ----------------- | ------------- | ----------- |
| `granted_at`      | `timestamptz` | Nullable    |
| `revoked_at`      | `timestamptz` | Nullable    |
| `properties`      | `jsonb`       |             |
| `benefit_id`      | `uuid`        |             |
| `subscription_id` | `uuid`        | Nullable    |
| `order_id`        | `uuid`        | Nullable    |
| `id`              | `uuid`        | Primary     |
| `created_at`      | `timestamptz` |             |
| `modified_at`     | `timestamptz` | Nullable    |
| `deleted_at`      | `timestamptz` | Nullable    |
| `customer_id`     | `uuid`        |             |
| `error`           | `jsonb`       | Nullable    |
| `member_id`       | `uuid`        | Nullable    |

## Table `benefits`

### Columns

| Name                | Type          | Constraints |
| ------------------- | ------------- | ----------- |
| `type`              | `varchar`     |             |
| `description`       | `text`        |             |
| `is_tax_applicable` | `bool`        |             |
| `selectable`        | `bool`        |             |
| `deletable`         | `bool`        |             |
| `properties`        | `jsonb`       |             |
| `organization_id`   | `uuid`        |             |
| `id`                | `uuid`        | Primary     |
| `created_at`        | `timestamptz` |             |
| `modified_at`       | `timestamptz` | Nullable    |
| `deleted_at`        | `timestamptz` | Nullable    |
| `user_metadata`     | `jsonb`       |             |

## Table `billing_entry`

### Columns

| Name               | Type          | Constraints |
| ------------------ | ------------- | ----------- |
| `start_timestamp`  | `timestamptz` |             |
| `end_timestamp`    | `timestamptz` |             |
| `direction`        | `varchar`     |             |
| `customer_id`      | `uuid`        |             |
| `product_price_id` | `uuid`        |             |
| `subscription_id`  | `uuid`        | Nullable    |
| `event_id`         | `uuid`        |             |
| `order_item_id`    | `uuid`        | Nullable    |
| `id`               | `uuid`        | Primary     |
| `created_at`       | `timestamptz` |             |
| `modified_at`      | `timestamptz` | Nullable    |
| `deleted_at`       | `timestamptz` | Nullable    |
| `amount`           | `int4`        | Nullable    |
| `currency`         | `varchar`     | Nullable    |
| `type`             | `varchar`     |             |
| `discount_id`      | `uuid`        | Nullable    |
| `discount_amount`  | `int4`        | Nullable    |

## Table `campaigns`

### Columns

| Name                   | Type          | Constraints |
| ---------------------- | ------------- | ----------- |
| `code`                 | `varchar`     | Nullable    |
| `name`                 | `varchar`     |             |
| `starts_at`            | `timestamptz` | Nullable    |
| `ends_at`              | `timestamptz` | Nullable    |
| `max_redemptions`      | `int4`        | Nullable    |
| `max_user_redemptions` | `int4`        | Nullable    |
| `fee_percent`          | `int4`        | Nullable    |
| `fee_fixed`            | `int4`        | Nullable    |
| `user_metadata`        | `jsonb`       |             |
| `id`                   | `uuid`        | Primary     |
| `created_at`           | `timestamptz` |             |
| `modified_at`          | `timestamptz` | Nullable    |
| `deleted_at`           | `timestamptz` | Nullable    |
| `fee_credit`           | `int4`        | Nullable    |
| `fee_credit_title`     | `varchar`     | Nullable    |
| `notes`                | `text`        | Nullable    |

## Table `checkout_link_products`

### Columns

| Name               | Type          | Constraints |
| ------------------ | ------------- | ----------- |
| `checkout_link_id` | `uuid`        |             |
| `product_id`       | `uuid`        |             |
| `order`            | `int4`        |             |
| `id`               | `uuid`        | Primary     |
| `created_at`       | `timestamptz` |             |
| `modified_at`      | `timestamptz` | Nullable    |
| `deleted_at`       | `timestamptz` | Nullable    |

## Table `checkout_links`

### Columns

| Name                      | Type          | Constraints |
| ------------------------- | ------------- | ----------- |
| `payment_processor`       | `varchar`     |             |
| `client_secret`           | `varchar`     |             |
| `success_url`             | `varchar`     | Nullable    |
| `user_metadata`           | `jsonb`       |             |
| `id`                      | `uuid`        | Primary     |
| `created_at`              | `timestamptz` |             |
| `modified_at`             | `timestamptz` | Nullable    |
| `deleted_at`              | `timestamptz` | Nullable    |
| `label`                   | `varchar`     | Nullable    |
| `allow_discount_codes`    | `bool`        |             |
| `discount_id`             | `uuid`        | Nullable    |
| `organization_id`         | `uuid`        |             |
| `require_billing_address` | `bool`        |             |
| `trial_interval`          | `varchar`     | Nullable    |
| `trial_interval_count`    | `int4`        | Nullable    |

## Table `checkout_products`

### Columns

| Name          | Type          | Constraints |
| ------------- | ------------- | ----------- |
| `checkout_id` | `uuid`        |             |
| `product_id`  | `uuid`        |             |
| `order`       | `int4`        |             |
| `id`          | `uuid`        | Primary     |
| `created_at`  | `timestamptz` |             |
| `modified_at` | `timestamptz` | Nullable    |
| `deleted_at`  | `timestamptz` | Nullable    |

## Table `checkouts`

### Columns

| Name                         | Type          | Constraints |
| ---------------------------- | ------------- | ----------- |
| `payment_processor`          | `varchar`     |             |
| `status`                     | `varchar`     |             |
| `client_secret`              | `varchar`     |             |
| `expires_at`                 | `timestamptz` |             |
| `user_metadata`              | `jsonb`       |             |
| `payment_processor_metadata` | `jsonb`       |             |
| `amount`                     | `int4`        |             |
| `tax_amount`                 | `int4`        | Nullable    |
| `currency`                   | `varchar`     |             |
| `product_id`                 | `uuid`        | Nullable    |
| `product_price_id`           | `uuid`        | Nullable    |
| `customer_id`                | `uuid`        | Nullable    |
| `customer_name`              | `varchar`     | Nullable    |
| `customer_email`             | `varchar`     | Nullable    |
| `customer_ip_address`        | `varchar`     | Nullable    |
| `customer_billing_address`   | `jsonb`       | Nullable    |
| `id`                         | `uuid`        | Primary     |
| `created_at`                 | `timestamptz` |             |
| `modified_at`                | `timestamptz` | Nullable    |
| `deleted_at`                 | `timestamptz` | Nullable    |
| `customer_tax_id`            | `jsonb`       | Nullable    |
| `success_url`                | `varchar`     | Nullable    |
| `embed_origin`               | `varchar`     | Nullable    |
| `subscription_id`            | `uuid`        | Nullable    |
| `custom_field_data`          | `jsonb`       |             |
| `allow_discount_codes`       | `bool`        |             |
| `discount_id`                | `uuid`        | Nullable    |
| `customer_metadata`          | `jsonb`       |             |
| `external_customer_id`       | `varchar`     | Nullable    |
| `require_billing_address`    | `bool`        |             |
| `is_business_customer`       | `bool`        |             |
| `customer_billing_name`      | `varchar`     | Nullable    |
| `tax_processor_id`           | `varchar`     | Nullable    |
| `trial_end`                  | `timestamptz` | Nullable    |
| `trial_interval`             | `varchar`     | Nullable    |
| `trial_interval_count`       | `int4`        | Nullable    |
| `seats`                      | `int4`        | Nullable    |
| `return_url`                 | `varchar`     | Nullable    |
| `organization_id`            | `uuid`        |             |
| `allow_trial`                | `bool`        | Nullable    |
| `tax_processor`              | `varchar`     | Nullable    |
| `tax_rate`                   | `jsonb`       | Nullable    |
| `taxability_reason`          | `varchar`     | Nullable    |
| `analytics_metadata`         | `jsonb`       | Nullable    |

## Table `custom_fields`

### Columns

| Name              | Type          | Constraints |
| ----------------- | ------------- | ----------- |
| `type`            | `varchar`     |             |
| `slug`            | `citext`      |             |
| `name`            | `varchar`     |             |
| `properties`      | `jsonb`       |             |
| `organization_id` | `uuid`        |             |
| `user_metadata`   | `jsonb`       |             |
| `id`              | `uuid`        | Primary     |
| `created_at`      | `timestamptz` |             |
| `modified_at`     | `timestamptz` | Nullable    |
| `deleted_at`      | `timestamptz` | Nullable    |

## Table `customer_meters`

### Columns

| Name                     | Type          | Constraints |
| ------------------------ | ------------- | ----------- |
| `id`                     | `uuid`        | Primary     |
| `created_at`             | `timestamptz` |             |
| `modified_at`            | `timestamptz` | Nullable    |
| `deleted_at`             | `timestamptz` | Nullable    |
| `customer_id`            | `uuid`        |             |
| `meter_id`               | `uuid`        |             |
| `last_balanced_event_id` | `uuid`        | Nullable    |
| `consumed_units`         | `numeric`     |             |
| `credited_units`         | `int8`        |             |
| `balance`                | `numeric`     |             |
| `activated_at`           | `timestamptz` | Nullable    |

## Table `customer_seats`

### Columns

| Name                          | Type          | Constraints |
| ----------------------------- | ------------- | ----------- |
| `subscription_id`             | `uuid`        | Nullable    |
| `status`                      | `varchar`     |             |
| `customer_id`                 | `uuid`        | Nullable    |
| `invitation_token`            | `varchar`     | Nullable    |
| `claimed_at`                  | `timestamptz` | Nullable    |
| `revoked_at`                  | `timestamptz` | Nullable    |
| `metadata`                    | `jsonb`       | Nullable    |
| `id`                          | `uuid`        | Primary     |
| `created_at`                  | `timestamptz` |             |
| `modified_at`                 | `timestamptz` | Nullable    |
| `deleted_at`                  | `timestamptz` | Nullable    |
| `invitation_token_expires_at` | `timestamptz` | Nullable    |
| `order_id`                    | `uuid`        | Nullable    |
| `member_id`                   | `uuid`        | Nullable    |
| `email`                       | `varchar`     | Nullable    |

## Table `customer_session_codes`

### Columns

| Name          | Type          | Constraints |
| ------------- | ------------- | ----------- |
| `code`        | `bpchar`      | Unique      |
| `expires_at`  | `timestamptz` |             |
| `customer_id` | `uuid`        |             |
| `id`          | `uuid`        | Primary     |
| `created_at`  | `timestamptz` |             |
| `modified_at` | `timestamptz` | Nullable    |
| `deleted_at`  | `timestamptz` | Nullable    |
| `email`       | `varchar`     |             |

## Table `customer_sessions`

### Columns

| Name          | Type          | Constraints |
| ------------- | ------------- | ----------- |
| `token`       | `bpchar`      | Unique      |
| `expires_at`  | `timestamptz` |             |
| `customer_id` | `uuid`        |             |
| `id`          | `uuid`        | Primary     |
| `created_at`  | `timestamptz` |             |
| `modified_at` | `timestamptz` | Nullable    |
| `deleted_at`  | `timestamptz` | Nullable    |
| `return_url`  | `varchar`     | Nullable    |

## Table `customers`

### Columns

| Name                        | Type          | Constraints |
| --------------------------- | ------------- | ----------- |
| `id`                        | `uuid`        | Primary     |
| `created_at`                | `timestamptz` |             |
| `modified_at`               | `timestamptz` | Nullable    |
| `deleted_at`                | `timestamptz` | Nullable    |
| `organization_id`           | `uuid`        |             |
| `email`                     | `varchar`     |             |
| `email_verified`            | `bool`        |             |
| `stripe_customer_id`        | `varchar`     | Nullable    |
| `name`                      | `varchar`     | Nullable    |
| `billing_address`           | `jsonb`       | Nullable    |
| `tax_id`                    | `jsonb`       | Nullable    |
| `oauth_accounts`            | `jsonb`       |             |
| `legacy_user_id`            | `uuid`        | Nullable    |
| `user_metadata`             | `jsonb`       |             |
| `external_id`               | `varchar`     | Nullable    |
| `billing_name`              | `varchar`     | Nullable    |
| `default_payment_method_id` | `uuid`        | Nullable    |
| `meters_dirtied_at`         | `timestamptz` | Nullable    |
| `meters_updated_at`         | `timestamptz` | Nullable    |
| `invoice_next_number`       | `int4`        |             |
| `short_id`                  | `int8`        |             |
| `search_vector`             | `tsvector`    | Nullable    |

## Table `discount_products`

### Columns

| Name          | Type          | Constraints |
| ------------- | ------------- | ----------- |
| `discount_id` | `uuid`        | Primary     |
| `product_id`  | `uuid`        | Primary     |
| `id`          | `uuid`        | Primary     |
| `created_at`  | `timestamptz` |             |
| `modified_at` | `timestamptz` | Nullable    |
| `deleted_at`  | `timestamptz` | Nullable    |

## Table `discount_redemptions`

### Columns

| Name              | Type          | Constraints |
| ----------------- | ------------- | ----------- |
| `discount_id`     | `uuid`        |             |
| `checkout_id`     | `uuid`        | Nullable    |
| `id`              | `uuid`        | Primary     |
| `created_at`      | `timestamptz` |             |
| `modified_at`     | `timestamptz` | Nullable    |
| `deleted_at`      | `timestamptz` | Nullable    |
| `subscription_id` | `uuid`        | Nullable    |

## Table `discounts`

### Columns

| Name                 | Type          | Constraints |
| -------------------- | ------------- | ----------- |
| `name`               | `citext`      |             |
| `type`               | `varchar`     |             |
| `code`               | `varchar`     | Nullable    |
| `starts_at`          | `timestamptz` | Nullable    |
| `ends_at`            | `timestamptz` | Nullable    |
| `max_redemptions`    | `int4`        | Nullable    |
| `duration`           | `varchar`     |             |
| `duration_in_months` | `int4`        | Nullable    |
| `organization_id`    | `uuid`        |             |
| `user_metadata`      | `jsonb`       |             |
| `id`                 | `uuid`        | Primary     |
| `created_at`         | `timestamptz` |             |
| `modified_at`        | `timestamptz` | Nullable    |
| `deleted_at`         | `timestamptz` | Nullable    |
| `amount`             | `int4`        | Nullable    |
| `currency`           | `varchar`     | Nullable    |
| `basis_points`       | `int4`        | Nullable    |
| `redemptions_count`  | `int4`        |             |

## Table `disputes`

### Columns

| Name                         | Type          | Constraints |
| ---------------------------- | ------------- | ----------- |
| `id`                         | `uuid`        | Primary     |
| `created_at`                 | `timestamptz` |             |
| `modified_at`                | `timestamptz` | Nullable    |
| `deleted_at`                 | `timestamptz` | Nullable    |
| `status`                     | `varchar`     |             |
| `amount`                     | `int4`        |             |
| `tax_amount`                 | `int4`        |             |
| `currency`                   | `varchar`     |             |
| `payment_processor_id`       | `varchar`     | Nullable    |
| `dispute_alert_processor`    | `varchar`     | Nullable    |
| `dispute_alert_processor_id` | `varchar`     | Nullable    |
| `order_id`                   | `uuid`        |             |
| `payment_id`                 | `uuid`        |             |
| `payment_processor`          | `varchar`     | Nullable    |

## Table `downloadables`

### Columns

| Name                 | Type          | Constraints |
| -------------------- | ------------- | ----------- |
| `file_id`            | `uuid`        |             |
| `status`             | `varchar`     |             |
| `benefit_id`         | `uuid`        |             |
| `downloaded`         | `int4`        |             |
| `last_downloaded_at` | `timestamptz` | Nullable    |
| `id`                 | `uuid`        | Primary     |
| `created_at`         | `timestamptz` |             |
| `modified_at`        | `timestamptz` | Nullable    |
| `deleted_at`         | `timestamptz` | Nullable    |
| `customer_id`        | `uuid`        |             |

## Table `email_verification`

### Columns

| Name          | Type          | Constraints |
| ------------- | ------------- | ----------- |
| `email`       | `varchar`     |             |
| `token_hash`  | `varchar`     |             |
| `expires_at`  | `timestamptz` |             |
| `user_id`     | `uuid`        |             |
| `id`          | `uuid`        | Primary     |
| `created_at`  | `timestamptz` |             |
| `modified_at` | `timestamptz` | Nullable    |
| `deleted_at`  | `timestamptz` | Nullable    |

## Table `event_types`

### Columns

| Name                      | Type          | Constraints |
| ------------------------- | ------------- | ----------- |
| `name`                    | `varchar`     |             |
| `label`                   | `varchar`     |             |
| `organization_id`         | `uuid`        |             |
| `id`                      | `uuid`        | Primary     |
| `created_at`              | `timestamptz` |             |
| `modified_at`             | `timestamptz` | Nullable    |
| `deleted_at`              | `timestamptz` | Nullable    |
| `label_property_selector` | `varchar`     | Nullable    |

## Table `events`

### Columns

| Name                   | Type          | Constraints |
| ---------------------- | ------------- | ----------- |
| `id`                   | `uuid`        | Primary     |
| `timestamp`            | `timestamptz` |             |
| `name`                 | `varchar`     |             |
| `source`               | `varchar`     |             |
| `customer_id`          | `uuid`        | Nullable    |
| `external_customer_id` | `varchar`     | Nullable    |
| `organization_id`      | `uuid`        |             |
| `user_metadata`        | `jsonb`       |             |
| `ingested_at`          | `timestamptz` |             |
| `external_id`          | `varchar`     | Nullable    |
| `parent_id`            | `uuid`        | Nullable    |
| `root_id`              | `uuid`        | Nullable    |
| `event_type_id`        | `uuid`        | Nullable    |

## Table `events_closure`

### Columns

| Name            | Type   | Constraints |
| --------------- | ------ | ----------- |
| `ancestor_id`   | `uuid` | Primary     |
| `descendant_id` | `uuid` | Primary     |
| `depth`         | `int8` |             |

## Table `external_events`

### Columns

| Name          | Type          | Constraints |
| ------------- | ------------- | ----------- |
| `id`          | `uuid`        | Primary     |
| `created_at`  | `timestamptz` |             |
| `modified_at` | `timestamptz` | Nullable    |
| `deleted_at`  | `timestamptz` | Nullable    |
| `source`      | `varchar`     |             |
| `external_id` | `varchar`     |             |
| `task_name`   | `varchar`     |             |
| `handled_at`  | `timestamptz` | Nullable    |
| `data`        | `jsonb`       |             |

## Table `files`

### Columns

| Name                     | Type          | Constraints |
| ------------------------ | ------------- | ----------- |
| `organization_id`        | `uuid`        |             |
| `name`                   | `varchar`     |             |
| `version`                | `varchar`     | Nullable    |
| `path`                   | `varchar`     |             |
| `mime_type`              | `varchar`     |             |
| `size`                   | `int8`        |             |
| `service`                | `varchar`     |             |
| `last_modified_at`       | `timestamptz` | Nullable    |
| `storage_version`        | `varchar`     | Nullable    |
| `checksum_etag`          | `varchar`     | Nullable    |
| `checksum_sha256_base64` | `varchar`     | Nullable    |
| `checksum_sha256_hex`    | `varchar`     | Nullable    |
| `is_uploaded`            | `bool`        |             |
| `is_enabled`             | `bool`        |             |
| `id`                     | `uuid`        | Primary     |
| `created_at`             | `timestamptz` |             |
| `modified_at`            | `timestamptz` | Nullable    |
| `deleted_at`             | `timestamptz` | Nullable    |

## Table `held_balances`

### Columns

| Name                     | Type          | Constraints |
| ------------------------ | ------------- | ----------- |
| `organization_id`        | `uuid`        | Nullable    |
| `account_id`             | `uuid`        | Nullable    |
| `payment_transaction_id` | `uuid`        |             |
| `amount`                 | `int4`        |             |
| `pledge_id`              | `uuid`        | Nullable    |
| `order_id`               | `uuid`        | Nullable    |
| `issue_reward_id`        | `uuid`        | Nullable    |
| `id`                     | `uuid`        | Primary     |
| `created_at`             | `timestamptz` |             |
| `modified_at`            | `timestamptz` | Nullable    |
| `deleted_at`             | `timestamptz` | Nullable    |

## Table `issue_rewards`

### Columns

| Name              | Type          | Constraints |
| ----------------- | ------------- | ----------- |
| `share_thousands` | `int8`        |             |
| `github_username` | `varchar`     | Nullable    |
| `organization_id` | `uuid`        | Nullable    |
| `user_id`         | `uuid`        | Nullable    |
| `id`              | `uuid`        | Primary     |
| `created_at`      | `timestamptz` |             |
| `modified_at`     | `timestamptz` | Nullable    |
| `deleted_at`      | `timestamptz` | Nullable    |
| `issue_reference` | `varchar`     |             |

## Table `license_key_activations`

### Columns

| Name             | Type          | Constraints |
| ---------------- | ------------- | ----------- |
| `license_key_id` | `uuid`        |             |
| `label`          | `varchar`     |             |
| `id`             | `uuid`        | Primary     |
| `created_at`     | `timestamptz` |             |
| `modified_at`    | `timestamptz` | Nullable    |
| `deleted_at`     | `timestamptz` | Nullable    |
| `meta`           | `jsonb`       |             |
| `conditions`     | `jsonb`       |             |

## Table `license_keys`

### Columns

| Name                | Type          | Constraints |
| ------------------- | ------------- | ----------- |
| `benefit_id`        | `uuid`        |             |
| `key`               | `varchar`     |             |
| `status`            | `varchar`     |             |
| `expires_at`        | `timestamptz` | Nullable    |
| `id`                | `uuid`        | Primary     |
| `created_at`        | `timestamptz` |             |
| `modified_at`       | `timestamptz` | Nullable    |
| `deleted_at`        | `timestamptz` | Nullable    |
| `limit_activations` | `int4`        | Nullable    |
| `validations`       | `int4`        |             |
| `last_validated_at` | `timestamptz` | Nullable    |
| `usage`             | `int4`        |             |
| `limit_usage`       | `int4`        | Nullable    |
| `organization_id`   | `uuid`        |             |
| `customer_id`       | `uuid`        |             |

## Table `login_codes`

### Columns

| Name          | Type          | Constraints |
| ------------- | ------------- | ----------- |
| `code_hash`   | `bpchar`      |             |
| `expires_at`  | `timestamptz` |             |
| `email`       | `varchar`     |             |
| `user_id`     | `uuid`        | Nullable    |
| `id`          | `uuid`        | Primary     |
| `created_at`  | `timestamptz` |             |
| `modified_at` | `timestamptz` | Nullable    |
| `deleted_at`  | `timestamptz` | Nullable    |

## Table `member_sessions`

### Columns

| Name          | Type          | Constraints |
| ------------- | ------------- | ----------- |
| `id`          | `uuid`        | Primary     |
| `created_at`  | `timestamptz` |             |
| `modified_at` | `timestamptz` | Nullable    |
| `deleted_at`  | `timestamptz` | Nullable    |
| `token`       | `bpchar`      | Unique      |
| `expires_at`  | `timestamptz` |             |
| `return_url`  | `varchar`     | Nullable    |
| `member_id`   | `uuid`        |             |

## Table `members`

### Columns

| Name              | Type          | Constraints |
| ----------------- | ------------- | ----------- |
| `customer_id`     | `uuid`        |             |
| `email`           | `varchar`     |             |
| `name`            | `varchar`     | Nullable    |
| `external_id`     | `varchar`     | Nullable    |
| `role`            | `varchar`     |             |
| `id`              | `uuid`        | Primary     |
| `created_at`      | `timestamptz` |             |
| `modified_at`     | `timestamptz` | Nullable    |
| `deleted_at`      | `timestamptz` | Nullable    |
| `organization_id` | `uuid`        |             |

## Table `meter_events`

### Columns

| Name                   | Type          | Constraints |
| ---------------------- | ------------- | ----------- |
| `meter_id`             | `uuid`        | Primary     |
| `event_id`             | `uuid`        | Primary     |
| `customer_id`          | `uuid`        | Nullable    |
| `external_customer_id` | `varchar`     | Nullable    |
| `organization_id`      | `uuid`        |             |
| `ingested_at`          | `timestamptz` |             |
| `timestamp`            | `timestamptz` |             |

## Table `meters`

### Columns

| Name                   | Type          | Constraints |
| ---------------------- | ------------- | ----------- |
| `name`                 | `varchar`     |             |
| `filter`               | `jsonb`       |             |
| `aggregation`          | `jsonb`       |             |
| `organization_id`      | `uuid`        |             |
| `id`                   | `uuid`        | Primary     |
| `created_at`           | `timestamptz` |             |
| `modified_at`          | `timestamptz` | Nullable    |
| `deleted_at`           | `timestamptz` | Nullable    |
| `user_metadata`        | `jsonb`       |             |
| `last_billed_event_id` | `uuid`        | Nullable    |
| `archived_at`          | `timestamptz` | Nullable    |

## Table `notification_recipients`

### Columns

| Name              | Type          | Constraints |
| ----------------- | ------------- | ----------- |
| `user_id`         | `uuid`        |             |
| `platform`        | `varchar`     |             |
| `expo_push_token` | `varchar`     |             |
| `id`              | `uuid`        | Primary     |
| `created_at`      | `timestamptz` |             |
| `modified_at`     | `timestamptz` | Nullable    |
| `deleted_at`      | `timestamptz` | Nullable    |

## Table `notifications`

### Columns

| Name          | Type          | Constraints |
| ------------- | ------------- | ----------- |
| `user_id`     | `uuid`        |             |
| `type`        | `varchar`     |             |
| `payload`     | `jsonb`       |             |
| `id`          | `uuid`        | Primary     |
| `created_at`  | `timestamptz` |             |
| `modified_at` | `timestamptz` | Nullable    |
| `deleted_at`  | `timestamptz` | Nullable    |

## Table `oauth2_authorization_codes`

### Columns

| Name                    | Type          | Constraints |
| ----------------------- | ------------- | ----------- |
| `id`                    | `uuid`        | Primary     |
| `created_at`            | `timestamptz` |             |
| `modified_at`           | `timestamptz` | Nullable    |
| `deleted_at`            | `timestamptz` | Nullable    |
| `sub_type`              | `varchar`     |             |
| `user_id`               | `uuid`        | Nullable    |
| `organization_id`       | `uuid`        | Nullable    |
| `code`                  | `varchar`     | Unique      |
| `client_id`             | `varchar`     |             |
| `redirect_uri`          | `text`        | Nullable    |
| `response_type`         | `text`        | Nullable    |
| `scope`                 | `text`        | Nullable    |
| `nonce`                 | `text`        | Nullable    |
| `auth_time`             | `int4`        |             |
| `code_challenge`        | `text`        | Nullable    |
| `code_challenge_method` | `varchar`     | Nullable    |
| `acr`                   | `text`        | Nullable    |
| `amr`                   | `text`        | Nullable    |

## Table `oauth2_clients`

### Columns

| Name                        | Type          | Constraints |
| --------------------------- | ------------- | ----------- |
| `registration_access_token` | `varchar`     |             |
| `user_id`                   | `uuid`        | Nullable    |
| `id`                        | `uuid`        | Primary     |
| `created_at`                | `timestamptz` |             |
| `modified_at`               | `timestamptz` | Nullable    |
| `deleted_at`                | `timestamptz` | Nullable    |
| `client_id`                 | `varchar`     | Unique      |
| `client_secret`             | `varchar`     |             |
| `client_id_issued_at`       | `int4`        |             |
| `client_secret_expires_at`  | `int4`        |             |
| `client_metadata`           | `text`        | Nullable    |
| `rate_limit_group`          | `varchar`     |             |
| `first_party`               | `bool`        |             |

## Table `oauth2_grants`

### Columns

| Name              | Type          | Constraints |
| ----------------- | ------------- | ----------- |
| `client_id`       | `varchar`     |             |
| `scope`           | `text`        |             |
| `user_id`         | `uuid`        | Nullable    |
| `organization_id` | `uuid`        | Nullable    |
| `id`              | `uuid`        | Primary     |
| `created_at`      | `timestamptz` |             |
| `modified_at`     | `timestamptz` | Nullable    |
| `deleted_at`      | `timestamptz` | Nullable    |

## Table `oauth2_tokens`

### Columns

| Name                       | Type          | Constraints |
| -------------------------- | ------------- | ----------- |
| `nonce`                    | `varchar`     | Nullable    |
| `id`                       | `uuid`        | Primary     |
| `created_at`               | `timestamptz` |             |
| `modified_at`              | `timestamptz` | Nullable    |
| `deleted_at`               | `timestamptz` | Nullable    |
| `client_id`                | `varchar`     |             |
| `token_type`               | `varchar`     | Nullable    |
| `access_token`             | `varchar`     | Unique      |
| `refresh_token`            | `varchar`     | Nullable    |
| `scope`                    | `text`        | Nullable    |
| `issued_at`                | `int4`        |             |
| `access_token_revoked_at`  | `int4`        |             |
| `refresh_token_revoked_at` | `int4`        |             |
| `expires_in`               | `int4`        |             |
| `sub_type`                 | `varchar`     |             |
| `user_id`                  | `uuid`        | Nullable    |
| `organization_id`          | `uuid`        | Nullable    |

## Table `oauth_accounts`

### Columns

| Name                       | Type          | Constraints |
| -------------------------- | ------------- | ----------- |
| `platform`                 | `varchar`     |             |
| `access_token`             | `varchar`     |             |
| `expires_at`               | `int4`        | Nullable    |
| `refresh_token`            | `varchar`     | Nullable    |
| `account_id`               | `varchar`     |             |
| `account_email`            | `varchar`     |             |
| `account_username`         | `varchar`     | Nullable    |
| `user_id`                  | `uuid`        |             |
| `id`                       | `uuid`        | Primary     |
| `created_at`               | `timestamptz` |             |
| `modified_at`              | `timestamptz` | Nullable    |
| `deleted_at`               | `timestamptz` | Nullable    |
| `refresh_token_expires_at` | `int4`        | Nullable    |

## Table `order_items`

### Columns

| Name               | Type          | Constraints |
| ------------------ | ------------- | ----------- |
| `label`            | `varchar`     |             |
| `amount`           | `int4`        |             |
| `tax_amount`       | `int4`        |             |
| `proration`        | `bool`        |             |
| `order_id`         | `uuid`        |             |
| `product_price_id` | `uuid`        | Nullable    |
| `id`               | `uuid`        | Primary     |
| `created_at`       | `timestamptz` |             |
| `modified_at`      | `timestamptz` | Nullable    |
| `deleted_at`       | `timestamptz` | Nullable    |

## Table `orders`

### Columns

| Name                           | Type          | Constraints     |
| ------------------------------ | ------------- | --------------- |
| `subtotal_amount`              | `int4`        |                 |
| `tax_amount`                   | `int4`        |                 |
| `currency`                     | `varchar`     |                 |
| `stripe_invoice_id`            | `varchar`     | Nullable Unique |
| `product_id`                   | `uuid`        | Nullable        |
| `subscription_id`              | `uuid`        | Nullable        |
| `id`                           | `uuid`        | Primary         |
| `created_at`                   | `timestamptz` |                 |
| `modified_at`                  | `timestamptz` | Nullable        |
| `deleted_at`                   | `timestamptz` | Nullable        |
| `checkout_id`                  | `uuid`        | Nullable        |
| `user_metadata`                | `jsonb`       |                 |
| `billing_reason`               | `varchar`     |                 |
| `custom_field_data`            | `jsonb`       |                 |
| `discount_id`                  | `uuid`        | Nullable        |
| `billing_address`              | `jsonb`       | Nullable        |
| `customer_id`                  | `uuid`        |                 |
| `status`                       | `varchar`     |                 |
| `refunded_amount`              | `int4`        |                 |
| `refunded_tax_amount`          | `int4`        |                 |
| `discount_amount`              | `int4`        |                 |
| `billing_name`                 | `varchar`     | Nullable        |
| `taxability_reason`            | `varchar`     | Nullable        |
| `tax_id`                       | `jsonb`       | Nullable        |
| `tax_rate`                     | `jsonb`       | Nullable        |
| `invoice_number`               | `varchar`     | Unique          |
| `invoice_path`                 | `varchar`     | Nullable        |
| `tax_transaction_processor_id` | `varchar`     | Nullable        |
| `tax_calculation_processor_id` | `varchar`     | Nullable        |
| `next_payment_attempt_at`      | `timestamptz` | Nullable        |
| `payment_lock_acquired_at`     | `timestamptz` | Nullable        |
| `platform_fee_amount`          | `int4`        |                 |
| `applied_balance_amount`       | `int4`        |                 |
| `seats`                        | `int4`        | Nullable        |
| `platform_fee_currency`        | `varchar`     | Nullable        |
| `refunds_blocked_at`           | `timestamptz` | Nullable        |
| `search_vector`                | `tsvector`    | Nullable        |
| `tax_processor`                | `varchar`     | Nullable        |

## Table `organization_access_tokens`

### Columns

| Name              | Type          | Constraints |
| ----------------- | ------------- | ----------- |
| `token`           | `bpchar`      | Unique      |
| `scope`           | `text`        |             |
| `expires_at`      | `timestamptz` | Nullable    |
| `comment`         | `varchar`     |             |
| `last_used_at`    | `timestamptz` | Nullable    |
| `organization_id` | `uuid`        |             |
| `id`              | `uuid`        | Primary     |
| `created_at`      | `timestamptz` |             |
| `modified_at`     | `timestamptz` | Nullable    |
| `deleted_at`      | `timestamptz` | Nullable    |

## Table `organization_reviews`

### Columns

| Name                            | Type          | Constraints |
| ------------------------------- | ------------- | ----------- |
| `organization_id`               | `uuid`        |             |
| `verdict`                       | `varchar`     |             |
| `risk_score`                    | `float8`      |             |
| `violated_sections`             | `jsonb`       |             |
| `reason`                        | `text`        |             |
| `timed_out`                     | `bool`        |             |
| `model_used`                    | `varchar`     |             |
| `organization_details_snapshot` | `jsonb`       |             |
| `validated_at`                  | `timestamptz` |             |
| `id`                            | `uuid`        | Primary     |
| `created_at`                    | `timestamptz` |             |
| `modified_at`                   | `timestamptz` | Nullable    |
| `deleted_at`                    | `timestamptz` | Nullable    |
| `appeal_submitted_at`           | `timestamptz` | Nullable    |
| `appeal_reason`                 | `text`        | Nullable    |
| `appeal_reviewed_at`            | `timestamptz` | Nullable    |
| `appeal_decision`               | `varchar`     | Nullable    |

## Table `organizations`

### Columns

| Name                           | Type          | Constraints |
| ------------------------------ | ------------- | ----------- |
| `slug`                         | `citext`      | Unique      |
| `avatar_url`                   | `varchar`     | Nullable    |
| `account_id`                   | `uuid`        | Nullable    |
| `onboarded_at`                 | `timestamptz` | Nullable    |
| `blocked_at`                   | `timestamptz` | Nullable    |
| `profile_settings`             | `jsonb`       |             |
| `feature_settings`             | `jsonb`       |             |
| `bio`                          | `varchar`     | Nullable    |
| `name`                         | `varchar`     |             |
| `company`                      | `varchar`     | Nullable    |
| `blog`                         | `varchar`     | Nullable    |
| `location`                     | `varchar`     | Nullable    |
| `email`                        | `varchar`     | Nullable    |
| `twitter_username`             | `varchar`     | Nullable    |
| `id`                           | `uuid`        | Primary     |
| `created_at`                   | `timestamptz` |             |
| `modified_at`                  | `timestamptz` | Nullable    |
| `deleted_at`                   | `timestamptz` | Nullable    |
| `subscription_settings`        | `jsonb`       |             |
| `website`                      | `varchar`     | Nullable    |
| `socials`                      | `jsonb`       |             |
| `details`                      | `jsonb`       |             |
| `details_submitted_at`         | `timestamptz` | Nullable    |
| `customer_invoice_prefix`      | `varchar`     |             |
| `customer_invoice_next_number` | `int4`        |             |
| `notification_settings`        | `jsonb`       |             |
| `status`                       | `varchar`     |             |
| `next_review_threshold`        | `int4`        |             |
| `rate_limit_group`             | `varchar`     |             |
| `status_updated_at`            | `timestamptz` | Nullable    |
| `customer_email_settings`      | `jsonb`       |             |
| `order_settings`               | `jsonb`       |             |
| `internal_notes`               | `text`        | Nullable    |
| `initially_reviewed_at`        | `timestamptz` | Nullable    |
| `ai_onboarding_completed_at`   | `timestamptz` | Nullable    |
| `customer_portal_settings`     | `jsonb`       |             |
| `default_presentment_currency` | `varchar`     |             |

## Table `payment_methods`

### Columns

| Name              | Type          | Constraints |
| ----------------- | ------------- | ----------- |
| `id`              | `uuid`        | Primary     |
| `created_at`      | `timestamptz` |             |
| `modified_at`     | `timestamptz` | Nullable    |
| `deleted_at`      | `timestamptz` | Nullable    |
| `processor`       | `varchar`     |             |
| `processor_id`    | `varchar`     |             |
| `type`            | `varchar`     |             |
| `method_metadata` | `jsonb`       |             |
| `customer_id`     | `uuid`        |             |

## Table `payments`

### Columns

| Name                 | Type          | Constraints |
| -------------------- | ------------- | ----------- |
| `id`                 | `uuid`        | Primary     |
| `created_at`         | `timestamptz` |             |
| `modified_at`        | `timestamptz` | Nullable    |
| `deleted_at`         | `timestamptz` | Nullable    |
| `processor`          | `varchar`     |             |
| `status`             | `varchar`     |             |
| `amount`             | `int4`        |             |
| `currency`           | `varchar`     |             |
| `method`             | `varchar`     |             |
| `method_metadata`    | `jsonb`       |             |
| `customer_email`     | `varchar`     | Nullable    |
| `processor_id`       | `varchar`     |             |
| `decline_reason`     | `varchar`     | Nullable    |
| `decline_message`    | `varchar`     | Nullable    |
| `risk_level`         | `varchar`     | Nullable    |
| `risk_score`         | `int2`        | Nullable    |
| `organization_id`    | `uuid`        |             |
| `checkout_id`        | `uuid`        | Nullable    |
| `order_id`           | `uuid`        | Nullable    |
| `processor_metadata` | `jsonb`       |             |
| `wallet_id`          | `uuid`        | Nullable    |

## Table `payouts`

### Columns

| Name               | Type          | Constraints |
| ------------------ | ------------- | ----------- |
| `id`               | `uuid`        | Primary     |
| `created_at`       | `timestamptz` |             |
| `modified_at`      | `timestamptz` | Nullable    |
| `deleted_at`       | `timestamptz` | Nullable    |
| `processor`        | `varchar`     |             |
| `processor_id`     | `varchar`     | Nullable    |
| `status`           | `varchar`     |             |
| `currency`         | `varchar`     |             |
| `amount`           | `int8`        |             |
| `fees_amount`      | `int8`        |             |
| `account_currency` | `varchar`     |             |
| `account_amount`   | `int8`        |             |
| `account_id`       | `uuid`        |             |
| `invoice_number`   | `varchar`     |             |
| `invoice_path`     | `varchar`     | Nullable    |
| `paid_at`          | `timestamptz` | Nullable    |

## Table `personal_access_tokens`

### Columns

| Name           | Type          | Constraints |
| -------------- | ------------- | ----------- |
| `user_id`      | `uuid`        |             |
| `expires_at`   | `timestamptz` | Nullable    |
| `comment`      | `varchar`     |             |
| `last_used_at` | `timestamptz` | Nullable    |
| `id`           | `uuid`        | Primary     |
| `created_at`   | `timestamptz` |             |
| `modified_at`  | `timestamptz` | Nullable    |
| `deleted_at`   | `timestamptz` | Nullable    |
| `token`        | `bpchar`      | Unique      |
| `scope`        | `text`        |             |

## Table `pledge_transactions`

### Columns

| Name              | Type          | Constraints |
| ----------------- | ------------- | ----------- |
| `pledge_id`       | `uuid`        |             |
| `type`            | `varchar`     |             |
| `amount`          | `int8`        |             |
| `transaction_id`  | `varchar`     | Nullable    |
| `issue_reward_id` | `uuid`        | Nullable    |
| `id`              | `uuid`        | Primary     |
| `created_at`      | `timestamptz` |             |
| `modified_at`     | `timestamptz` | Nullable    |
| `deleted_at`      | `timestamptz` | Nullable    |

## Table `pledges`

### Columns

| Name                           | Type          | Constraints |
| ------------------------------ | ------------- | ----------- |
| `organization_id`              | `uuid`        | Nullable    |
| `payment_id`                   | `varchar`     | Nullable    |
| `invoice_id`                   | `varchar`     | Nullable    |
| `invoice_hosted_url`           | `varchar`     | Nullable    |
| `transfer_id`                  | `varchar`     | Nullable    |
| `email`                        | `varchar`     | Nullable    |
| `amount`                       | `int8`        |             |
| `fee`                          | `int8`        |             |
| `amount_received`              | `int8`        | Nullable    |
| `state`                        | `varchar`     |             |
| `type`                         | `varchar`     |             |
| `scheduled_payout_at`          | `timestamptz` | Nullable    |
| `dispute_reason`               | `varchar`     | Nullable    |
| `disputed_by_user_id`          | `uuid`        | Nullable    |
| `disputed_at`                  | `timestamptz` | Nullable    |
| `refunded_at`                  | `timestamptz` | Nullable    |
| `by_user_id`                   | `uuid`        | Nullable    |
| `by_organization_id`           | `uuid`        | Nullable    |
| `on_behalf_of_organization_id` | `uuid`        | Nullable    |
| `created_by_user_id`           | `uuid`        | Nullable    |
| `id`                           | `uuid`        | Primary     |
| `created_at`                   | `timestamptz` |             |
| `modified_at`                  | `timestamptz` | Nullable    |
| `deleted_at`                   | `timestamptz` | Nullable    |
| `currency`                     | `varchar`     |             |
| `issue_reference`              | `varchar`     |             |

## Table `processor_transactions`

### Columns

| Name           | Type          | Constraints |
| -------------- | ------------- | ----------- |
| `id`           | `uuid`        | Primary     |
| `timestamp`    | `timestamptz` |             |
| `processor`    | `varchar`     |             |
| `processor_id` | `varchar`     |             |
| `type`         | `varchar`     |             |
| `currency`     | `varchar`     |             |
| `amount`       | `int8`        |             |
| `fee`          | `int8`        |             |
| `description`  | `text`        | Nullable    |
| `raw`          | `jsonb`       |             |

## Table `product_benefits`

### Columns

| Name          | Type          | Constraints |
| ------------- | ------------- | ----------- |
| `product_id`  | `uuid`        | Primary     |
| `benefit_id`  | `uuid`        | Primary     |
| `order`       | `int4`        |             |
| `id`          | `uuid`        | Primary     |
| `created_at`  | `timestamptz` |             |
| `modified_at` | `timestamptz` | Nullable    |
| `deleted_at`  | `timestamptz` | Nullable    |

## Table `product_custom_fields`

### Columns

| Name              | Type          | Constraints |
| ----------------- | ------------- | ----------- |
| `product_id`      | `uuid`        | Primary     |
| `custom_field_id` | `uuid`        | Primary     |
| `order`           | `int4`        |             |
| `required`        | `bool`        |             |
| `id`              | `uuid`        | Primary     |
| `created_at`      | `timestamptz` |             |
| `modified_at`     | `timestamptz` | Nullable    |
| `deleted_at`      | `timestamptz` | Nullable    |

## Table `product_medias`

### Columns

| Name          | Type          | Constraints |
| ------------- | ------------- | ----------- |
| `product_id`  | `uuid`        | Primary     |
| `file_id`     | `uuid`        | Primary     |
| `order`       | `int4`        |             |
| `id`          | `uuid`        | Primary     |
| `created_at`  | `timestamptz` |             |
| `modified_at` | `timestamptz` | Nullable    |
| `deleted_at`  | `timestamptz` | Nullable    |

## Table `product_prices`

### Columns

| Name                  | Type          | Constraints |
| --------------------- | ------------- | ----------- |
| `type`                | `varchar`     | Nullable    |
| `recurring_interval`  | `varchar`     | Nullable    |
| `price_amount`        | `int4`        | Nullable    |
| `price_currency`      | `varchar`     | Nullable    |
| `is_archived`         | `bool`        |             |
| `product_id`          | `uuid`        |             |
| `id`                  | `uuid`        | Primary     |
| `created_at`          | `timestamptz` |             |
| `modified_at`         | `timestamptz` | Nullable    |
| `deleted_at`          | `timestamptz` | Nullable    |
| `amount_type`         | `varchar`     |             |
| `minimum_amount`      | `int4`        | Nullable    |
| `maximum_amount`      | `int4`        | Nullable    |
| `preset_amount`       | `int4`        | Nullable    |
| `unit_amount`         | `numeric`     | Nullable    |
| `cap_amount`          | `int4`        | Nullable    |
| `meter_id`            | `uuid`        | Nullable    |
| `seat_tiers`          | `jsonb`       | Nullable    |
| `source`              | `varchar`     |             |
| `checkout_product_id` | `uuid`        | Nullable    |

## Table `products`

### Columns

| Name                       | Type          | Constraints |
| -------------------------- | ------------- | ----------- |
| `name`                     | `citext`      |             |
| `description`              | `text`        | Nullable    |
| `is_archived`              | `bool`        |             |
| `organization_id`          | `uuid`        |             |
| `id`                       | `uuid`        | Primary     |
| `created_at`               | `timestamptz` |             |
| `modified_at`              | `timestamptz` | Nullable    |
| `deleted_at`               | `timestamptz` | Nullable    |
| `user_metadata`            | `jsonb`       |             |
| `is_tax_applicable`        | `bool`        |             |
| `recurring_interval`       | `varchar`     | Nullable    |
| `trial_interval`           | `varchar`     | Nullable    |
| `trial_interval_count`     | `int4`        | Nullable    |
| `tax_code`                 | `varchar`     |             |
| `recurring_interval_count` | `int4`        | Nullable    |
| `search_vector`            | `tsvector`    | Nullable    |

## Table `refunds`

### Columns

| Name                               | Type          | Constraints |
| ---------------------------------- | ------------- | ----------- |
| `id`                               | `uuid`        | Primary     |
| `status`                           | `varchar`     |             |
| `reason`                           | `varchar`     |             |
| `amount`                           | `int4`        |             |
| `tax_amount`                       | `int4`        |             |
| `currency`                         | `varchar`     |             |
| `comment`                          | `varchar`     | Nullable    |
| `failure_reason`                   | `varchar`     | Nullable    |
| `destination_details`              | `jsonb`       |             |
| `order_id`                         | `uuid`        | Nullable    |
| `subscription_id`                  | `uuid`        | Nullable    |
| `organization_id`                  | `uuid`        | Nullable    |
| `customer_id`                      | `uuid`        | Nullable    |
| `pledge_id`                        | `uuid`        | Nullable    |
| `user_metadata`                    | `jsonb`       |             |
| `revoke_benefits`                  | `bool`        |             |
| `processor`                        | `varchar`     |             |
| `processor_id`                     | `varchar`     |             |
| `processor_reason`                 | `varchar`     |             |
| `processor_receipt_number`         | `varchar`     | Nullable    |
| `processor_balance_transaction_id` | `varchar`     | Nullable    |
| `created_at`                       | `timestamptz` |             |
| `modified_at`                      | `timestamptz` | Nullable    |
| `deleted_at`                       | `timestamptz` | Nullable    |
| `tax_transaction_processor_id`     | `varchar`     | Nullable    |
| `dispute_id`                       | `uuid`        | Nullable    |
| `payment_id`                       | `uuid`        |             |

## Table `subscription_meters`

### Columns

| Name              | Type          | Constraints |
| ----------------- | ------------- | ----------- |
| `id`              | `uuid`        | Primary     |
| `created_at`      | `timestamptz` |             |
| `modified_at`     | `timestamptz` | Nullable    |
| `deleted_at`      | `timestamptz` | Nullable    |
| `subscription_id` | `uuid`        |             |
| `meter_id`        | `uuid`        |             |
| `consumed_units`  | `numeric`     |             |
| `credited_units`  | `int4`        |             |
| `amount`          | `int4`        |             |

## Table `subscription_product_prices`

### Columns

| Name               | Type          | Constraints |
| ------------------ | ------------- | ----------- |
| `subscription_id`  | `uuid`        | Primary     |
| `product_price_id` | `uuid`        | Primary     |
| `amount`           | `int4`        |             |
| `id`               | `uuid`        | Primary     |
| `created_at`       | `timestamptz` |             |
| `modified_at`      | `timestamptz` | Nullable    |
| `deleted_at`       | `timestamptz` | Nullable    |

## Table `subscriptions`

### Columns

| Name                            | Type          | Constraints |
| ------------------------------- | ------------- | ----------- |
| `status`                        | `varchar`     |             |
| `current_period_start`          | `timestamptz` |             |
| `current_period_end`            | `timestamptz` | Nullable    |
| `cancel_at_period_end`          | `bool`        |             |
| `started_at`                    | `timestamptz` | Nullable    |
| `ended_at`                      | `timestamptz` | Nullable    |
| `product_id`                    | `uuid`        |             |
| `id`                            | `uuid`        | Primary     |
| `created_at`                    | `timestamptz` |             |
| `modified_at`                   | `timestamptz` | Nullable    |
| `deleted_at`                    | `timestamptz` | Nullable    |
| `amount`                        | `int4`        |             |
| `currency`                      | `varchar`     |             |
| `recurring_interval`            | `varchar`     |             |
| `checkout_id`                   | `uuid`        | Nullable    |
| `user_metadata`                 | `jsonb`       |             |
| `custom_field_data`             | `jsonb`       |             |
| `discount_id`                   | `uuid`        | Nullable    |
| `customer_id`                   | `uuid`        |             |
| `canceled_at`                   | `timestamptz` | Nullable    |
| `ends_at`                       | `timestamptz` | Nullable    |
| `customer_cancellation_reason`  | `varchar`     | Nullable    |
| `customer_cancellation_comment` | `text`        | Nullable    |
| `payment_method_id`             | `uuid`        | Nullable    |
| `tax_exempted`                  | `bool`        |             |
| `scheduler_locked_at`           | `timestamptz` | Nullable    |
| `trial_start`                   | `timestamptz` | Nullable    |
| `trial_end`                     | `timestamptz` | Nullable    |
| `legacy_stripe_subscription_id` | `varchar`     | Nullable    |
| `seats`                         | `int4`        | Nullable    |
| `recurring_interval_count`      | `int4`        |             |
| `past_due_at`                   | `timestamptz` | Nullable    |
| `discount_applied_at`           | `timestamptz` | Nullable    |

## Table `transactions`

### Columns

| Name                              | Type          | Constraints |
| --------------------------------- | ------------- | ----------- |
| `type`                            | `varchar`     |             |
| `processor`                       | `varchar`     | Nullable    |
| `currency`                        | `varchar`     |             |
| `amount`                          | `int8`        |             |
| `account_currency`                | `varchar`     |             |
| `account_amount`                  | `int8`        |             |
| `tax_amount`                      | `int8`        |             |
| `tax_country`                     | `varchar`     | Nullable    |
| `tax_state`                       | `varchar`     | Nullable    |
| `processor_fee_type`              | `varchar`     | Nullable    |
| `balance_correlation_key`         | `varchar`     | Nullable    |
| `platform_fee_type`               | `varchar`     | Nullable    |
| `customer_id`                     | `varchar`     | Nullable    |
| `charge_id`                       | `varchar`     | Nullable    |
| `dispute_id`                      | `uuid`        | Nullable    |
| `transfer_id`                     | `varchar`     | Nullable    |
| `transfer_reversal_id`            | `varchar`     | Nullable    |
| `fee_balance_transaction_id`      | `varchar`     | Nullable    |
| `account_id`                      | `uuid`        | Nullable    |
| `payment_user_id`                 | `uuid`        | Nullable    |
| `payment_organization_id`         | `uuid`        | Nullable    |
| `pledge_id`                       | `uuid`        | Nullable    |
| `order_id`                        | `uuid`        | Nullable    |
| `issue_reward_id`                 | `uuid`        | Nullable    |
| `payment_transaction_id`          | `uuid`        | Nullable    |
| `balance_reversal_transaction_id` | `uuid`        | Nullable    |
| `payout_transaction_id`           | `uuid`        | Nullable    |
| `incurred_by_transaction_id`      | `uuid`        | Nullable    |
| `id`                              | `uuid`        | Primary     |
| `created_at`                      | `timestamptz` |             |
| `modified_at`                     | `timestamptz` | Nullable    |
| `deleted_at`                      | `timestamptz` | Nullable    |
| `risk_level`                      | `varchar`     | Nullable    |
| `risk_score`                      | `int4`        | Nullable    |
| `payment_customer_id`             | `uuid`        | Nullable    |
| `refund_id`                       | `uuid`        | Nullable    |
| `payout_id`                       | `uuid`        | Nullable    |
| `presentment_amount`              | `int8`        | Nullable    |
| `presentment_tax_amount`          | `int8`        | Nullable    |
| `presentment_currency`            | `varchar`     | Nullable    |
| `tax_filing_amount`               | `int8`        | Nullable    |
| `tax_filing_currency`             | `varchar`     | Nullable    |
| `tax_processor_id`                | `varchar`     | Nullable    |
| `tax_processor`                   | `varchar`     | Nullable    |

## Table `trial_redemptions`

### Columns

| Name                         | Type          | Constraints |
| ---------------------------- | ------------- | ----------- |
| `customer_email`             | `varchar`     |             |
| `payment_method_fingerprint` | `varchar`     | Nullable    |
| `customer_id`                | `uuid`        |             |
| `product_id`                 | `uuid`        | Nullable    |
| `id`                         | `uuid`        | Primary     |
| `created_at`                 | `timestamptz` |             |
| `modified_at`                | `timestamptz` | Nullable    |
| `deleted_at`                 | `timestamptz` | Nullable    |

## Table `user_notifications`

### Columns

| Name                        | Type   | Constraints |
| --------------------------- | ------ | ----------- |
| `user_id`                   | `uuid` | Primary     |
| `last_read_notification_id` | `uuid` | Nullable    |

## Table `user_organizations`

### Columns

| Name              | Type          | Constraints |
| ----------------- | ------------- | ----------- |
| `user_id`         | `uuid`        | Primary     |
| `organization_id` | `uuid`        | Primary     |
| `created_at`      | `timestamptz` |             |
| `modified_at`     | `timestamptz` | Nullable    |
| `deleted_at`      | `timestamptz` | Nullable    |

## Table `user_sessions`

### Columns

| Name          | Type          | Constraints |
| ------------- | ------------- | ----------- |
| `token`       | `bpchar`      | Unique      |
| `expires_at`  | `timestamptz` |             |
| `user_agent`  | `text`        |             |
| `user_id`     | `uuid`        |             |
| `id`          | `uuid`        | Primary     |
| `created_at`  | `timestamptz` |             |
| `modified_at` | `timestamptz` | Nullable    |
| `deleted_at`  | `timestamptz` | Nullable    |
| `scopes`      | `_varchar`    |             |

## Table `users`

### Columns

| Name                           | Type          | Constraints     |
| ------------------------------ | ------------- | --------------- |
| `email`                        | `varchar`     |                 |
| `email_verified`               | `bool`        |                 |
| `avatar_url`                   | `text`        | Nullable        |
| `account_id`                   | `uuid`        | Nullable        |
| `accepted_terms_of_service`    | `bool`        |                 |
| `stripe_customer_id`           | `varchar`     | Nullable Unique |
| `blocked_at`                   | `timestamptz` | Nullable        |
| `id`                           | `uuid`        | Primary         |
| `created_at`                   | `timestamptz` |                 |
| `modified_at`                  | `timestamptz` | Nullable        |
| `deleted_at`                   | `timestamptz` | Nullable        |
| `meta`                         | `jsonb`       |                 |
| `identity_verification_status` | `varchar`     |                 |
| `identity_verification_id`     | `varchar`     | Nullable Unique |
| `is_admin`                     | `bool`        |                 |

## Table `wallet_transactions`

### Columns

| Name                           | Type          | Constraints |
| ------------------------------ | ------------- | ----------- |
| `timestamp`                    | `timestamptz` |             |
| `currency`                     | `varchar`     |             |
| `amount`                       | `int8`        |             |
| `wallet_id`                    | `uuid`        |             |
| `tax_amount`                   | `int8`        | Nullable    |
| `tax_calculation_processor_id` | `varchar`     | Nullable    |
| `order_id`                     | `uuid`        | Nullable    |
| `refund_id`                    | `uuid`        | Nullable    |
| `id`                           | `uuid`        | Primary     |
| `tax_processor`                | `varchar`     | Nullable    |
| `tax_rate`                     | `jsonb`       | Nullable    |
| `taxability_reason`            | `varchar`     | Nullable    |

## Table `wallets`

### Columns

| Name          | Type          | Constraints |
| ------------- | ------------- | ----------- |
| `currency`    | `varchar`     |             |
| `customer_id` | `uuid`        | Unique      |
| `id`          | `uuid`        | Primary     |
| `created_at`  | `timestamptz` |             |
| `modified_at` | `timestamptz` | Nullable    |
| `deleted_at`  | `timestamptz` | Nullable    |
| `type`        | `varchar`     |             |

## Table `webhook_deliveries`

### Columns

| Name                  | Type          | Constraints |
| --------------------- | ------------- | ----------- |
| `webhook_endpoint_id` | `uuid`        |             |
| `webhook_event_id`    | `uuid`        |             |
| `http_code`           | `int4`        | Nullable    |
| `succeeded`           | `bool`        |             |
| `id`                  | `uuid`        | Primary     |
| `created_at`          | `timestamptz` |             |
| `modified_at`         | `timestamptz` | Nullable    |
| `deleted_at`          | `timestamptz` | Nullable    |
| `response`            | `text`        | Nullable    |

## Table `webhook_endpoints`

### Columns

| Name              | Type          | Constraints |
| ----------------- | ------------- | ----------- |
| `url`             | `varchar`     |             |
| `secret`          | `varchar`     |             |
| `organization_id` | `uuid`        |             |
| `events`          | `jsonb`       |             |
| `id`              | `uuid`        | Primary     |
| `created_at`      | `timestamptz` |             |
| `modified_at`     | `timestamptz` | Nullable    |
| `deleted_at`      | `timestamptz` | Nullable    |
| `format`          | `varchar`     |             |
| `enabled`         | `bool`        |             |

## Table `webhook_events`

### Columns

| Name                  | Type          | Constraints |
| --------------------- | ------------- | ----------- |
| `webhook_endpoint_id` | `uuid`        |             |
| `last_http_code`      | `int4`        | Nullable    |
| `succeeded`           | `bool`        | Nullable    |
| `payload`             | `varchar`     | Nullable    |
| `id`                  | `uuid`        | Primary     |
| `created_at`          | `timestamptz` |             |
| `modified_at`         | `timestamptz` | Nullable    |
| `deleted_at`          | `timestamptz` | Nullable    |
| `type`                | `varchar`     |             |
| `skipped`             | `bool`        |             |
