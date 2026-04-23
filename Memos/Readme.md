## Table `activity`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `int4` | Primary |
| `creator_id` | `int4` |  |
| `created_ts` | `int8` |  |
| `type` | `text` |  |
| `level` | `text` |  |
| `payload` | `jsonb` |  |

## Table `idp`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `int4` | Primary |
| `name` | `text` |  |
| `type` | `text` |  |
| `identifier_filter` | `text` |  |
| `config` | `jsonb` |  |

## Table `inbox`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `int4` | Primary |
| `created_ts` | `int8` |  |
| `sender_id` | `int4` |  |
| `receiver_id` | `int4` |  |
| `status` | `text` |  |
| `message` | `text` |  |

## Table `memo`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `int4` | Primary |
| `resource_name` | `text` |  Unique |
| `creator_id` | `int4` |  |
| `created_ts` | `int8` |  |
| `updated_ts` | `int8` |  |
| `row_status` | `text` |  |
| `content` | `text` |  |
| `visibility` | `text` |  |

## Table `memo_organizer`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `memo_id` | `int4` |  |
| `user_id` | `int4` |  |
| `pinned` | `int4` |  |

## Table `memo_relation`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `memo_id` | `int4` |  |
| `related_memo_id` | `int4` |  |
| `type` | `text` |  |

## Table `migration_history`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `version` | `text` | Primary |
| `created_ts` | `int8` |  |

## Table `reaction`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `int4` | Primary |
| `created_ts` | `int8` |  |
| `creator_id` | `int4` |  |
| `content_id` | `text` |  |
| `reaction_type` | `text` |  |

## Table `resource`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `int4` | Primary |
| `resource_name` | `text` |  Unique |
| `creator_id` | `int4` |  |
| `created_ts` | `int8` |  |
| `updated_ts` | `int8` |  |
| `filename` | `text` |  |
| `blob` | `bytea` |  Nullable |
| `external_link` | `text` |  |
| `type` | `text` |  |
| `size` | `int4` |  |
| `internal_path` | `text` |  |
| `memo_id` | `int4` |  Nullable |

## Table `storage`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `int4` | Primary |
| `name` | `text` |  |
| `type` | `text` |  |
| `config` | `jsonb` |  |

## Table `system_setting`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `name` | `text` | Primary |
| `value` | `text` |  |
| `description` | `text` |  |

## Table `tag`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `name` | `text` |  |
| `creator_id` | `int4` |  |

## Table `user`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `int4` | Primary |
| `created_ts` | `int8` |  |
| `updated_ts` | `int8` |  |
| `row_status` | `text` |  |
| `username` | `text` |  Unique |
| `role` | `text` |  |
| `email` | `text` |  |
| `nickname` | `text` |  |
| `password_hash` | `text` |  |
| `avatar_url` | `text` |  |

## Table `user_setting`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `user_id` | `int4` |  |
| `key` | `text` |  |
| `value` | `text` |  |

## Table `webhook`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `int4` | Primary |
| `created_ts` | `int8` |  |
| `updated_ts` | `int8` |  |
| `row_status` | `text` |  |
| `creator_id` | `int4` |  |
| `name` | `text` |  |
| `url` | `text` |  |

