
## Table `api_tokens`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `created_at` | `timestamptz` |  |
| `updated_at` | `timestamptz` |  |
| `id` | `uuid` | Primary |
| `token` | `varchar` |  Unique |
| `label` | `varchar` |  |
| `user_type` | `int2` |  |
| `created_by_id` | `uuid` |  Nullable |
| `updated_by_id` | `uuid` |  Nullable |
| `user_id` | `uuid` |  |

## Table `auth_group`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `int4` | Primary |
| `name` | `varchar` |  Unique |

## Table `auth_group_permissions`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `int8` | Primary |
| `group_id` | `int4` |  |
| `permission_id` | `int4` |  |

## Table `auth_permission`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `int4` | Primary |
| `name` | `varchar` |  |
| `content_type_id` | `int4` |  |
| `codename` | `varchar` |  |

## Table `authtoken_token`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `key` | `varchar` | Primary |
| `created` | `timestamptz` |  |
| `user_id` | `uuid` |  Unique |

## Table `cycle_issues`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `created_at` | `timestamptz` |  |
| `updated_at` | `timestamptz` |  |
| `id` | `uuid` | Primary |
| `created_by_id` | `uuid` |  Nullable |
| `cycle_id` | `uuid` |  |
| `issue_id` | `uuid` |  Unique |
| `project_id` | `uuid` |  |
| `updated_by_id` | `uuid` |  Nullable |
| `workspace_id` | `uuid` |  |

## Table `cycles`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `created_at` | `timestamptz` |  |
| `updated_at` | `timestamptz` |  |
| `id` | `uuid` | Primary |
| `name` | `varchar` |  |
| `description` | `text` |  |
| `start_date` | `date` |  Nullable |
| `end_date` | `date` |  Nullable |
| `status` | `varchar` |  |
| `created_by_id` | `uuid` |  Nullable |
| `owned_by_id` | `uuid` |  |
| `project_id` | `uuid` |  |
| `updated_by_id` | `uuid` |  Nullable |
| `workspace_id` | `uuid` |  |

## Table `django_content_type`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `int4` | Primary |
| `app_label` | `varchar` |  |
| `model` | `varchar` |  |

## Table `django_migrations`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `int8` | Primary |
| `app` | `varchar` |  |
| `name` | `varchar` |  |
| `applied` | `timestamptz` |  |

## Table `django_session`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `session_key` | `varchar` | Primary |
| `session_data` | `text` |  |
| `expire_date` | `timestamptz` |  |

## Table `file_assets`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `created_at` | `timestamptz` |  |
| `updated_at` | `timestamptz` |  |
| `id` | `uuid` | Primary |
| `attributes` | `jsonb` |  |
| `asset` | `varchar` |  |
| `created_by_id` | `uuid` |  Nullable |
| `updated_by_id` | `uuid` |  Nullable |
| `workspace_id` | `uuid` |  Nullable |

## Table `issue_activities`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `created_at` | `timestamptz` |  |
| `updated_at` | `timestamptz` |  |
| `id` | `uuid` | Primary |
| `verb` | `varchar` |  |
| `field` | `varchar` |  Nullable |
| `old_value` | `text` |  Nullable |
| `new_value` | `text` |  Nullable |
| `comment` | `text` |  |
| `attachments` | `_varchar` |  |
| `created_by_id` | `uuid` |  Nullable |
| `issue_id` | `uuid` |  |
| `issue_comment_id` | `uuid` |  Nullable |
| `project_id` | `uuid` |  |
| `updated_by_id` | `uuid` |  Nullable |
| `workspace_id` | `uuid` |  |
| `actor_id` | `uuid` |  Nullable |
| `new_identifier` | `uuid` |  Nullable |
| `old_identifier` | `uuid` |  Nullable |

## Table `issue_assignees`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `created_at` | `timestamptz` |  |
| `updated_at` | `timestamptz` |  |
| `id` | `uuid` | Primary |
| `assignee_id` | `uuid` |  |
| `created_by_id` | `uuid` |  Nullable |
| `issue_id` | `uuid` |  |
| `project_id` | `uuid` |  |
| `updated_by_id` | `uuid` |  Nullable |
| `workspace_id` | `uuid` |  |

## Table `issue_blockers`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `created_at` | `timestamptz` |  |
| `updated_at` | `timestamptz` |  |
| `id` | `uuid` | Primary |
| `block_id` | `uuid` |  |
| `blocked_by_id` | `uuid` |  |
| `created_by_id` | `uuid` |  Nullable |
| `project_id` | `uuid` |  |
| `updated_by_id` | `uuid` |  Nullable |
| `workspace_id` | `uuid` |  |

## Table `issue_comments`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `created_at` | `timestamptz` |  |
| `updated_at` | `timestamptz` |  |
| `id` | `uuid` | Primary |
| `comment_stripped` | `text` |  |
| `attachments` | `_varchar` |  |
| `created_by_id` | `uuid` |  Nullable |
| `issue_id` | `uuid` |  |
| `project_id` | `uuid` |  |
| `updated_by_id` | `uuid` |  Nullable |
| `workspace_id` | `uuid` |  |
| `actor_id` | `uuid` |  Nullable |
| `comment_html` | `text` |  |
| `comment_json` | `jsonb` |  Nullable |

## Table `issue_labels`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `created_at` | `timestamptz` |  |
| `updated_at` | `timestamptz` |  |
| `id` | `uuid` | Primary |
| `created_by_id` | `uuid` |  Nullable |
| `issue_id` | `uuid` |  |
| `label_id` | `uuid` |  |
| `project_id` | `uuid` |  |
| `updated_by_id` | `uuid` |  Nullable |
| `workspace_id` | `uuid` |  |

## Table `issue_properties`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `created_at` | `timestamptz` |  |
| `updated_at` | `timestamptz` |  |
| `id` | `uuid` | Primary |
| `properties` | `jsonb` |  |
| `created_by_id` | `uuid` |  Nullable |
| `project_id` | `uuid` |  |
| `updated_by_id` | `uuid` |  Nullable |
| `user_id` | `uuid` |  |
| `workspace_id` | `uuid` |  |

## Table `issue_sequences`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `created_at` | `timestamptz` |  |
| `updated_at` | `timestamptz` |  |
| `id` | `uuid` | Primary |
| `sequence` | `int8` |  |
| `deleted` | `bool` |  |
| `created_by_id` | `uuid` |  Nullable |
| `issue_id` | `uuid` |  Nullable |
| `project_id` | `uuid` |  |
| `updated_by_id` | `uuid` |  Nullable |
| `workspace_id` | `uuid` |  |

## Table `issue_timelines`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `created_at` | `timestamptz` |  |
| `updated_at` | `timestamptz` |  |
| `id` | `uuid` | Primary |
| `sequence_id` | `float8` |  |
| `links` | `jsonb` |  |
| `created_by_id` | `uuid` |  Nullable |
| `issue_id` | `uuid` |  |
| `project_id` | `uuid` |  |
| `updated_by_id` | `uuid` |  Nullable |
| `workspace_id` | `uuid` |  |

## Table `issues`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `created_at` | `timestamptz` |  |
| `updated_at` | `timestamptz` |  |
| `id` | `uuid` | Primary |
| `name` | `varchar` |  |
| `description` | `jsonb` |  Nullable |
| `priority` | `varchar` |  Nullable |
| `start_date` | `date` |  Nullable |
| `target_date` | `date` |  Nullable |
| `sequence_id` | `int4` |  |
| `attachments` | `_varchar` |  |
| `created_by_id` | `uuid` |  Nullable |
| `parent_id` | `uuid` |  Nullable |
| `project_id` | `uuid` |  |
| `state_id` | `uuid` |  Nullable |
| `updated_by_id` | `uuid` |  Nullable |
| `workspace_id` | `uuid` |  |
| `description_html` | `text` |  Nullable |
| `description_stripped` | `text` |  Nullable |

## Table `labels`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `created_at` | `timestamptz` |  |
| `updated_at` | `timestamptz` |  |
| `id` | `uuid` | Primary |
| `name` | `varchar` |  |
| `description` | `text` |  |
| `created_by_id` | `uuid` |  Nullable |
| `project_id` | `uuid` |  |
| `updated_by_id` | `uuid` |  Nullable |
| `workspace_id` | `uuid` |  |
| `parent_id` | `uuid` |  Nullable |
| `colour` | `varchar` |  |

## Table `module_issues`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `created_at` | `timestamptz` |  |
| `updated_at` | `timestamptz` |  |
| `id` | `uuid` | Primary |
| `created_by_id` | `uuid` |  Nullable |
| `issue_id` | `uuid` |  Unique |
| `module_id` | `uuid` |  |
| `project_id` | `uuid` |  |
| `updated_by_id` | `uuid` |  Nullable |
| `workspace_id` | `uuid` |  |

## Table `module_links`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `created_at` | `timestamptz` |  |
| `updated_at` | `timestamptz` |  |
| `id` | `uuid` | Primary |
| `title` | `varchar` |  Nullable |
| `url` | `varchar` |  |
| `created_by_id` | `uuid` |  Nullable |
| `module_id` | `uuid` |  |
| `project_id` | `uuid` |  |
| `updated_by_id` | `uuid` |  Nullable |
| `workspace_id` | `uuid` |  |

## Table `module_members`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `created_at` | `timestamptz` |  |
| `updated_at` | `timestamptz` |  |
| `id` | `uuid` | Primary |
| `created_by_id` | `uuid` |  Nullable |
| `member_id` | `uuid` |  |
| `module_id` | `uuid` |  |
| `project_id` | `uuid` |  |
| `updated_by_id` | `uuid` |  Nullable |
| `workspace_id` | `uuid` |  |

## Table `modules`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `created_at` | `timestamptz` |  |
| `updated_at` | `timestamptz` |  |
| `id` | `uuid` | Primary |
| `name` | `varchar` |  |
| `description` | `text` |  |
| `description_text` | `jsonb` |  Nullable |
| `description_html` | `jsonb` |  Nullable |
| `start_date` | `date` |  Nullable |
| `target_date` | `date` |  Nullable |
| `status` | `varchar` |  |
| `created_by_id` | `uuid` |  Nullable |
| `lead_id` | `uuid` |  Nullable |
| `project_id` | `uuid` |  |
| `updated_by_id` | `uuid` |  Nullable |
| `workspace_id` | `uuid` |  |

## Table `project_identifiers`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `int8` | Primary |
| `created_at` | `timestamptz` |  |
| `updated_at` | `timestamptz` |  |
| `name` | `varchar` |  |
| `created_by_id` | `uuid` |  Nullable |
| `project_id` | `uuid` |  Unique |
| `updated_by_id` | `uuid` |  Nullable |
| `workspace_id` | `uuid` |  Nullable |

## Table `project_member_invites`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `created_at` | `timestamptz` |  |
| `updated_at` | `timestamptz` |  |
| `id` | `uuid` | Primary |
| `email` | `varchar` |  |
| `accepted` | `bool` |  |
| `token` | `varchar` |  |
| `message` | `text` |  Nullable |
| `responded_at` | `timestamptz` |  Nullable |
| `role` | `int2` |  |
| `created_by_id` | `uuid` |  Nullable |
| `project_id` | `uuid` |  |
| `updated_by_id` | `uuid` |  Nullable |
| `workspace_id` | `uuid` |  |

## Table `project_members`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `created_at` | `timestamptz` |  |
| `updated_at` | `timestamptz` |  |
| `id` | `uuid` | Primary |
| `comment` | `text` |  Nullable |
| `role` | `int2` |  |
| `created_by_id` | `uuid` |  Nullable |
| `member_id` | `uuid` |  Nullable |
| `project_id` | `uuid` |  |
| `updated_by_id` | `uuid` |  Nullable |
| `workspace_id` | `uuid` |  |
| `view_props` | `jsonb` |  Nullable |
| `default_props` | `jsonb` |  |

## Table `projects`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `created_at` | `timestamptz` |  |
| `updated_at` | `timestamptz` |  |
| `id` | `uuid` | Primary |
| `name` | `varchar` |  |
| `description` | `text` |  |
| `description_text` | `jsonb` |  Nullable |
| `description_html` | `jsonb` |  Nullable |
| `network` | `int2` |  |
| `identifier` | `varchar` |  |
| `slug` | `varchar` |  |
| `created_by_id` | `uuid` |  Nullable |
| `default_assignee_id` | `uuid` |  Nullable |
| `project_lead_id` | `uuid` |  Nullable |
| `updated_by_id` | `uuid` |  Nullable |
| `workspace_id` | `uuid` |  |
| `icon` | `varchar` |  Nullable |

## Table `shortcuts`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `created_at` | `timestamptz` |  |
| `updated_at` | `timestamptz` |  |
| `id` | `uuid` | Primary |
| `name` | `varchar` |  |
| `description` | `text` |  |
| `type` | `varchar` |  |
| `url` | `varchar` |  Nullable |
| `created_by_id` | `uuid` |  Nullable |
| `project_id` | `uuid` |  |
| `updated_by_id` | `uuid` |  Nullable |
| `workspace_id` | `uuid` |  |

## Table `social_login_connections`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `created_at` | `timestamptz` |  |
| `updated_at` | `timestamptz` |  |
| `id` | `uuid` | Primary |
| `medium` | `varchar` |  |
| `last_login_at` | `timestamptz` |  Nullable |
| `last_received_at` | `timestamptz` |  Nullable |
| `token_data` | `jsonb` |  Nullable |
| `extra_data` | `jsonb` |  Nullable |
| `created_by_id` | `uuid` |  Nullable |
| `updated_by_id` | `uuid` |  Nullable |
| `user_id` | `uuid` |  |

## Table `states`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `created_at` | `timestamptz` |  |
| `updated_at` | `timestamptz` |  |
| `id` | `uuid` | Primary |
| `name` | `varchar` |  |
| `description` | `text` |  |
| `color` | `varchar` |  |
| `slug` | `varchar` |  |
| `created_by_id` | `uuid` |  Nullable |
| `project_id` | `uuid` |  |
| `updated_by_id` | `uuid` |  Nullable |
| `workspace_id` | `uuid` |  |
| `sequence` | `float8` |  |
| `group` | `varchar` |  |

## Table `taggit_tag`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `int4` | Primary |
| `name` | `varchar` |  Unique |
| `slug` | `varchar` |  Unique |

## Table `taggit_taggeditem`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `int4` | Primary |
| `object_id` | `int4` |  |
| `content_type_id` | `int4` |  |
| `tag_id` | `int4` |  |

## Table `team_members`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `created_at` | `timestamptz` |  |
| `updated_at` | `timestamptz` |  |
| `id` | `uuid` | Primary |
| `created_by_id` | `uuid` |  Nullable |
| `member_id` | `uuid` |  |
| `team_id` | `uuid` |  |
| `updated_by_id` | `uuid` |  Nullable |
| `workspace_id` | `uuid` |  |

## Table `teams`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `created_at` | `timestamptz` |  |
| `updated_at` | `timestamptz` |  |
| `id` | `uuid` | Primary |
| `name` | `varchar` |  |
| `description` | `text` |  |
| `created_by_id` | `uuid` |  Nullable |
| `updated_by_id` | `uuid` |  Nullable |
| `workspace_id` | `uuid` |  |

## Table `token_blacklist_blacklistedtoken`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `int8` | Primary |
| `blacklisted_at` | `timestamptz` |  |
| `token_id` | `int8` |  Unique |

## Table `token_blacklist_outstandingtoken`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `int8` | Primary |
| `token` | `text` |  |
| `created_at` | `timestamptz` |  Nullable |
| `expires_at` | `timestamptz` |  |
| `user_id` | `uuid` |  Nullable |
| `jti` | `varchar` |  Unique |

## Table `users`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `password` | `varchar` |  |
| `last_login` | `timestamptz` |  Nullable |
| `id` | `uuid` | Primary |
| `username` | `varchar` |  Unique |
| `mobile_number` | `varchar` |  Nullable |
| `email` | `varchar` |  Nullable Unique |
| `first_name` | `varchar` |  |
| `last_name` | `varchar` |  |
| `avatar` | `varchar` |  |
| `date_joined` | `timestamptz` |  |
| `created_at` | `timestamptz` |  |
| `updated_at` | `timestamptz` |  |
| `last_location` | `varchar` |  |
| `created_location` | `varchar` |  |
| `is_superuser` | `bool` |  |
| `is_managed` | `bool` |  |
| `is_password_expired` | `bool` |  |
| `is_active` | `bool` |  |
| `is_staff` | `bool` |  |
| `is_email_verified` | `bool` |  |
| `is_password_autoset` | `bool` |  |
| `is_onboarded` | `bool` |  |
| `token` | `varchar` |  |
| `billing_address_country` | `varchar` |  |
| `billing_address` | `jsonb` |  Nullable |
| `has_billing_address` | `bool` |  |
| `user_timezone` | `varchar` |  |
| `last_active` | `timestamptz` |  Nullable |
| `last_login_time` | `timestamptz` |  Nullable |
| `last_logout_time` | `timestamptz` |  Nullable |
| `last_login_ip` | `varchar` |  |
| `last_logout_ip` | `varchar` |  |
| `last_login_medium` | `varchar` |  |
| `last_login_uagent` | `text` |  |
| `token_updated_at` | `timestamptz` |  Nullable |
| `last_workspace_id` | `uuid` |  Nullable |
| `my_issues_prop` | `jsonb` |  Nullable |
| `role` | `varchar` |  Nullable |
| `is_bot` | `bool` |  |

## Table `users_groups`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `int8` | Primary |
| `user_id` | `uuid` |  |
| `group_id` | `int4` |  |

## Table `users_user_permissions`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `int8` | Primary |
| `user_id` | `uuid` |  |
| `permission_id` | `int4` |  |

## Table `views`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `created_at` | `timestamptz` |  |
| `updated_at` | `timestamptz` |  |
| `id` | `uuid` | Primary |
| `name` | `varchar` |  |
| `description` | `text` |  |
| `query` | `jsonb` |  |
| `created_by_id` | `uuid` |  Nullable |
| `project_id` | `uuid` |  |
| `updated_by_id` | `uuid` |  Nullable |
| `workspace_id` | `uuid` |  |

## Table `workspace_member_invites`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `created_at` | `timestamptz` |  |
| `updated_at` | `timestamptz` |  |
| `id` | `uuid` | Primary |
| `email` | `varchar` |  |
| `accepted` | `bool` |  |
| `token` | `varchar` |  |
| `message` | `text` |  Nullable |
| `responded_at` | `timestamptz` |  Nullable |
| `role` | `int2` |  |
| `created_by_id` | `uuid` |  Nullable |
| `updated_by_id` | `uuid` |  Nullable |
| `workspace_id` | `uuid` |  |

## Table `workspace_members`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `created_at` | `timestamptz` |  |
| `updated_at` | `timestamptz` |  |
| `id` | `uuid` | Primary |
| `role` | `int2` |  |
| `created_by_id` | `uuid` |  Nullable |
| `member_id` | `uuid` |  |
| `updated_by_id` | `uuid` |  Nullable |
| `workspace_id` | `uuid` |  |
| `company_role` | `text` |  Nullable |
| `view_props` | `jsonb` |  Nullable |

## Table `workspaces`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `created_at` | `timestamptz` |  |
| `updated_at` | `timestamptz` |  |
| `id` | `uuid` | Primary |
| `name` | `varchar` |  |
| `logo` | `varchar` |  Nullable |
| `slug` | `varchar` |  Unique |
| `created_by_id` | `uuid` |  Nullable |
| `owner_id` | `uuid` |  |
| `updated_by_id` | `uuid` |  Nullable |
| `company_size` | `int4` |  |

