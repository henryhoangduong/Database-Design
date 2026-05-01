## Table `application_deployment`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `application_id` | `uuid` |  |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `commit_hash` | `text` |  Nullable |
| `container_id` | `text` |  Nullable |
| `container_name` | `text` |  Nullable |
| `container_image` | `text` |  Nullable |
| `container_status` | `text` |  Nullable |

## Table `application_deployment_status`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `application_deployment_id` | `uuid` |  |
| `status` | `text` |  |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |

## Table `application_logs`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `application_id` | `uuid` |  |
| `log` | `text` |  |
| `created_at` | `timestamptz` |  |
| `updated_at` | `timestamptz` |  |
| `application_deployment_id` | `uuid` |  Nullable |

## Table `application_status`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `application_id` | `uuid` |  |
| `status` | `status` |  |
| `created_at` | `timestamptz` |  |
| `updated_at` | `timestamptz` |  |

## Table `applications`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `name` | `text` |  |
| `port` | `int4` |  |
| `environment` | `environment` |  |
| `build_variables` | `text` |  |
| `environment_variables` | `text` |  |
| `build_pack` | `build_pack` |  |
| `repository` | `text` |  |
| `branch` | `text` |  |
| `pre_run_command` | `text` |  |
| `post_run_command` | `text` |  |
| `domain` | `text` |  |
| `user_id` | `uuid` |  |
| `created_at` | `timestamptz` |  |
| `updated_at` | `timestamptz` |  |
| `dockerfile_path` | `text` |  |
| `base_path` | `text` |  |
| `proxy_server` | `varchar` |  |
| `organization_id` | `uuid` |  |

## Table `audit_logs`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `user_id` | `uuid` |  Nullable |
| `organization_id` | `uuid` |  Nullable |
| `action` | `audit_action` |  |
| `resource_type` | `audit_resource_type` |  |
| `resource_id` | `uuid` |  |
| `old_values` | `jsonb` |  Nullable |
| `new_values` | `jsonb` |  Nullable |
| `metadata` | `jsonb` |  Nullable |
| `ip_address` | `text` |  Nullable |
| `user_agent` | `text` |  Nullable |
| `created_at` | `timestamptz` |  Nullable |
| `request_id` | `uuid` |  Nullable |

## Table `domains`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `user_id` | `uuid` |  |
| `created_at` | `timestamptz` |  |
| `updated_at` | `timestamptz` |  |
| `deleted_at` | `timestamptz` |  Nullable |
| `name` | `varchar` |  |
| `organization_id` | `uuid` |  |

## Table `github_connectors`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `app_id` | `varchar` |  |
| `slug` | `varchar` |  |
| `pem` | `text` |  |
| `client_id` | `varchar` |  |
| `client_secret` | `varchar` |  |
| `webhook_secret` | `varchar` |  |
| `installation_id` | `varchar` |  |
| `created_at` | `timestamptz` |  |
| `updated_at` | `timestamptz` |  |
| `deleted_at` | `timestamptz` |  Nullable |
| `user_id` | `uuid` |  |

## Table `migrations`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `int8` | Primary |
| `name` | `varchar` |  |
| `applied_at` | `timestamptz` |  |

## Table `notification_preferences`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `user_id` | `uuid` |  |
| `created_at` | `timestamptz` |  |
| `updated_at` | `timestamptz` |  |
| `deleted_at` | `timestamptz` |  Nullable |

## Table `organization_users`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `user_id` | `uuid` |  |
| `organization_id` | `uuid` |  |
| `role_id` | `uuid` |  |
| `created_at` | `timestamptz` |  |
| `updated_at` | `timestamptz` |  |
| `deleted_at` | `timestamptz` |  Nullable |

## Table `organizations`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `name` | `varchar` |  Unique |
| `description` | `text` |  Nullable |
| `created_at` | `timestamptz` |  |
| `updated_at` | `timestamptz` |  |
| `deleted_at` | `timestamptz` |  Nullable |

## Table `permissions`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `name` | `varchar` |  |
| `description` | `text` |  Nullable |
| `resource` | `varchar` |  |
| `created_at` | `timestamptz` |  |
| `updated_at` | `timestamptz` |  |
| `deleted_at` | `timestamptz` |  Nullable |

## Table `preference_item`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `preference_id` | `uuid` |  |
| `category` | `varchar` |  |
| `type` | `varchar` |  |
| `enabled` | `bool` |  |
| `created_at` | `timestamptz` |  |
| `updated_at` | `timestamptz` |  |

## Table `refresh_tokens`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `user_id` | `uuid` |  |
| `token` | `varchar` |  Unique |
| `expires_at` | `timestamptz` |  |
| `created_at` | `timestamptz` |  |
| `revoked_at` | `timestamptz` |  Nullable |

## Table `role_permissions`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `role_id` | `uuid` |  |
| `permission_id` | `uuid` |  |
| `created_at` | `timestamptz` |  |
| `updated_at` | `timestamptz` |  |
| `deleted_at` | `timestamptz` |  Nullable |

## Table `roles`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `name` | `varchar` |  Unique |
| `description` | `text` |  Nullable |
| `created_at` | `timestamptz` |  |
| `updated_at` | `timestamptz` |  |
| `deleted_at` | `timestamptz` |  Nullable |

## Table `smtp_configs`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `host` | `varchar` |  |
| `port` | `int4` |  |
| `username` | `varchar` |  |
| `password` | `varchar` |  |
| `from_email` | `varchar` |  |
| `from_name` | `varchar` |  |
| `security` | `varchar` |  |
| `created_at` | `timestamptz` |  |
| `updated_at` | `timestamptz` |  |
| `is_active` | `bool` |  |
| `user_id` | `uuid` |  |
| `organization_id` | `uuid` |  |

## Table `user_settings`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `user_id` | `uuid` |  Unique |
| `font_family` | `varchar` |  |
| `font_size` | `int4` |  |
| `theme` | `varchar` |  |
| `language` | `varchar` |  |
| `auto_update` | `bool` |  |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `deleted_at` | `timestamp` |  Nullable |

## Table `users`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `username` | `varchar` |  |
| `email` | `varchar` |  Unique |
| `password` | `varchar` |  |
| `avatar` | `varchar` |  Nullable |
| `created_at` | `timestamptz` |  |
| `updated_at` | `timestamptz` |  |
| `deleted_at` | `timestamptz` |  Nullable |
| `is_verified` | `bool` |  |
| `reset_token` | `varchar` |  Nullable |
| `type` | `varchar` |  |
| `two_factor_enabled` | `bool` |  |
| `two_factor_secret` | `text` |  Nullable |

## Table `verification_tokens`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `user_id` | `uuid` |  |
| `token` | `text` |  Unique |
| `expires_at` | `timestamptz` |  |
| `created_at` | `timestamptz` |  |

## Table `webhook_configs`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `type` | `varchar` |  |
| `webhook_url` | `text` |  |
| `is_active` | `bool` |  |
| `user_id` | `uuid` |  |
| `organization_id` | `uuid` |  |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |

