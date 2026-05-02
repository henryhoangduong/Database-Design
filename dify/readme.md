## Table `account_integrates`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `account_id` | `uuid` |  |
| `provider` | `varchar` |  |
| `open_id` | `varchar` |  |
| `encrypted_token` | `varchar` |  |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |

## Table `account_plugin_permissions`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `tenant_id` | `uuid` |  Unique |
| `install_permission` | `varchar` |  |
| `debug_permission` | `varchar` |  |

## Table `account_trial_app_records`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `account_id` | `uuid` |  |
| `app_id` | `uuid` |  |
| `count` | `int4` |  |
| `created_at` | `timestamp` |  |

## Table `accounts`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `name` | `varchar` |  |
| `email` | `varchar` |  |
| `password` | `varchar` |  Nullable |
| `password_salt` | `varchar` |  Nullable |
| `avatar` | `varchar` |  Nullable |
| `interface_language` | `varchar` |  Nullable |
| `interface_theme` | `varchar` |  Nullable |
| `timezone` | `varchar` |  Nullable |
| `last_login_at` | `timestamp` |  Nullable |
| `last_login_ip` | `varchar` |  Nullable |
| `status` | `varchar` |  |
| `initialized_at` | `timestamp` |  Nullable |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `last_active_at` | `timestamp` |  |

## Table `alembic_version`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `version_num` | `varchar` | Primary |

## Table `api_based_extensions`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `tenant_id` | `uuid` |  |
| `name` | `varchar` |  |
| `api_endpoint` | `varchar` |  |
| `api_key` | `text` |  |
| `created_at` | `timestamp` |  |

## Table `api_requests`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `tenant_id` | `uuid` |  |
| `api_token_id` | `uuid` |  |
| `path` | `varchar` |  |
| `request` | `text` |  Nullable |
| `response` | `text` |  Nullable |
| `ip` | `varchar` |  |
| `created_at` | `timestamp` |  |

## Table `api_tokens`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `app_id` | `uuid` |  Nullable |
| `type` | `varchar` |  |
| `token` | `varchar` |  |
| `last_used_at` | `timestamp` |  Nullable |
| `created_at` | `timestamp` |  |
| `tenant_id` | `uuid` |  Nullable |

## Table `app_annotation_hit_histories`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `app_id` | `uuid` |  |
| `annotation_id` | `uuid` |  |
| `source` | `text` |  |
| `question` | `text` |  |
| `account_id` | `uuid` |  |
| `created_at` | `timestamp` |  |
| `score` | `float8` |  |
| `message_id` | `uuid` |  |
| `annotation_question` | `text` |  |
| `annotation_content` | `text` |  |

## Table `app_annotation_settings`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `app_id` | `uuid` |  |
| `score_threshold` | `float8` |  |
| `collection_binding_id` | `uuid` |  |
| `created_user_id` | `uuid` |  |
| `created_at` | `timestamp` |  |
| `updated_user_id` | `uuid` |  |
| `updated_at` | `timestamp` |  |

## Table `app_dataset_joins`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `app_id` | `uuid` |  |
| `dataset_id` | `uuid` |  |
| `created_at` | `timestamp` |  |

## Table `app_mcp_servers`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `tenant_id` | `uuid` |  |
| `app_id` | `uuid` |  |
| `name` | `varchar` |  |
| `description` | `varchar` |  |
| `server_code` | `varchar` |  Unique |
| `status` | `varchar` |  |
| `parameters` | `text` |  |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |

## Table `app_model_configs`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `app_id` | `uuid` |  |
| `provider` | `varchar` |  Nullable |
| `model_id` | `varchar` |  Nullable |
| `configs` | `json` |  Nullable |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `opening_statement` | `text` |  Nullable |
| `suggested_questions` | `text` |  Nullable |
| `suggested_questions_after_answer` | `text` |  Nullable |
| `more_like_this` | `text` |  Nullable |
| `model` | `text` |  Nullable |
| `user_input_form` | `text` |  Nullable |
| `pre_prompt` | `text` |  Nullable |
| `agent_mode` | `text` |  Nullable |
| `speech_to_text` | `text` |  Nullable |
| `sensitive_word_avoidance` | `text` |  Nullable |
| `retriever_resource` | `text` |  Nullable |
| `dataset_query_variable` | `varchar` |  Nullable |
| `prompt_type` | `varchar` |  |
| `chat_prompt_config` | `text` |  Nullable |
| `completion_prompt_config` | `text` |  Nullable |
| `dataset_configs` | `text` |  Nullable |
| `external_data_tools` | `text` |  Nullable |
| `file_upload` | `text` |  Nullable |
| `text_to_speech` | `text` |  Nullable |
| `created_by` | `uuid` |  Nullable |
| `updated_by` | `uuid` |  Nullable |

## Table `app_triggers`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `tenant_id` | `uuid` |  |
| `app_id` | `uuid` |  |
| `node_id` | `varchar` |  |
| `trigger_type` | `varchar` |  |
| `title` | `varchar` |  |
| `provider_name` | `varchar` |  Nullable |
| `status` | `varchar` |  |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |

## Table `apps`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `tenant_id` | `uuid` |  |
| `name` | `varchar` |  |
| `mode` | `varchar` |  |
| `icon` | `varchar` |  Nullable |
| `icon_background` | `varchar` |  Nullable |
| `app_model_config_id` | `uuid` |  Nullable |
| `status` | `varchar` |  |
| `enable_site` | `bool` |  |
| `enable_api` | `bool` |  |
| `api_rpm` | `int4` |  |
| `api_rph` | `int4` |  |
| `is_demo` | `bool` |  |
| `is_public` | `bool` |  |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `is_universal` | `bool` |  |
| `workflow_id` | `uuid` |  Nullable |
| `description` | `text` |  |
| `tracing` | `text` |  Nullable |
| `max_active_requests` | `int4` |  Nullable |
| `icon_type` | `varchar` |  Nullable |
| `created_by` | `uuid` |  Nullable |
| `updated_by` | `uuid` |  Nullable |
| `use_icon_as_answer_icon` | `bool` |  |

## Table `celery_taskmeta`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `int4` | Primary |
| `task_id` | `varchar` |  Unique |
| `status` | `varchar` |  |
| `result` | `bytea` |  Nullable |
| `date_done` | `timestamp` |  Nullable |
| `traceback` | `text` |  Nullable |
| `name` | `varchar` |  Nullable |
| `args` | `bytea` |  Nullable |
| `kwargs` | `bytea` |  Nullable |
| `worker` | `varchar` |  Nullable |
| `retries` | `int4` |  Nullable |
| `queue` | `varchar` |  Nullable |

## Table `celery_tasksetmeta`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `int4` | Primary |
| `taskset_id` | `varchar` |  Unique |
| `result` | `bytea` |  Nullable |
| `date_done` | `timestamp` |  Nullable |

## Table `child_chunks`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `tenant_id` | `uuid` |  |
| `dataset_id` | `uuid` |  |
| `document_id` | `uuid` |  |
| `segment_id` | `uuid` |  |
| `position` | `int4` |  |
| `content` | `text` |  |
| `word_count` | `int4` |  |
| `index_node_id` | `varchar` |  Nullable |
| `index_node_hash` | `varchar` |  Nullable |
| `type` | `varchar` |  |
| `created_by` | `uuid` |  |
| `created_at` | `timestamp` |  |
| `updated_by` | `uuid` |  Nullable |
| `updated_at` | `timestamp` |  |
| `indexing_at` | `timestamp` |  Nullable |
| `completed_at` | `timestamp` |  Nullable |
| `error` | `text` |  Nullable |

## Table `conversations`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `app_id` | `uuid` |  |
| `app_model_config_id` | `uuid` |  Nullable |
| `model_provider` | `varchar` |  Nullable |
| `override_model_configs` | `text` |  Nullable |
| `model_id` | `varchar` |  Nullable |
| `mode` | `varchar` |  |
| `name` | `varchar` |  |
| `summary` | `text` |  Nullable |
| `inputs` | `json` |  |
| `introduction` | `text` |  Nullable |
| `system_instruction` | `text` |  Nullable |
| `system_instruction_tokens` | `int4` |  |
| `status` | `varchar` |  |
| `from_source` | `varchar` |  |
| `from_end_user_id` | `uuid` |  Nullable |
| `from_account_id` | `uuid` |  Nullable |
| `read_at` | `timestamp` |  Nullable |
| `read_account_id` | `uuid` |  Nullable |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `is_deleted` | `bool` |  |
| `invoke_from` | `varchar` |  Nullable |
| `dialogue_count` | `int4` |  |

## Table `data_source_api_key_auth_bindings`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `tenant_id` | `uuid` |  |
| `category` | `varchar` |  |
| `provider` | `varchar` |  |
| `credentials` | `text` |  Nullable |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `disabled` | `bool` |  Nullable |

## Table `data_source_oauth_bindings`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `tenant_id` | `uuid` |  |
| `access_token` | `varchar` |  |
| `provider` | `varchar` |  |
| `source_info` | `jsonb` |  |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `disabled` | `bool` |  Nullable |

## Table `dataset_auto_disable_logs`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `tenant_id` | `uuid` |  |
| `dataset_id` | `uuid` |  |
| `document_id` | `uuid` |  |
| `notified` | `bool` |  |
| `created_at` | `timestamp` |  |

## Table `dataset_collection_bindings`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `provider_name` | `varchar` |  |
| `model_name` | `varchar` |  |
| `collection_name` | `varchar` |  |
| `created_at` | `timestamp` |  |
| `type` | `varchar` |  |

## Table `dataset_keyword_tables`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `dataset_id` | `uuid` |  Unique |
| `keyword_table` | `text` |  |
| `data_source_type` | `varchar` |  |

## Table `dataset_metadata_bindings`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `tenant_id` | `uuid` |  |
| `dataset_id` | `uuid` |  |
| `metadata_id` | `uuid` |  |
| `document_id` | `uuid` |  |
| `created_at` | `timestamp` |  |
| `created_by` | `uuid` |  |

## Table `dataset_metadatas`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `tenant_id` | `uuid` |  |
| `dataset_id` | `uuid` |  |
| `type` | `varchar` |  |
| `name` | `varchar` |  |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `created_by` | `uuid` |  |
| `updated_by` | `uuid` |  Nullable |

## Table `dataset_permissions`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `dataset_id` | `uuid` |  |
| `account_id` | `uuid` |  |
| `has_permission` | `bool` |  |
| `created_at` | `timestamp` |  |
| `tenant_id` | `uuid` |  |

## Table `dataset_process_rules`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `dataset_id` | `uuid` |  |
| `mode` | `varchar` |  |
| `rules` | `text` |  Nullable |
| `created_by` | `uuid` |  |
| `created_at` | `timestamp` |  |

## Table `dataset_queries`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `dataset_id` | `uuid` |  |
| `content` | `text` |  |
| `source` | `varchar` |  |
| `source_app_id` | `uuid` |  Nullable |
| `created_by_role` | `varchar` |  |
| `created_by` | `uuid` |  |
| `created_at` | `timestamp` |  |

## Table `dataset_retriever_resources`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `message_id` | `uuid` |  |
| `position` | `int4` |  |
| `dataset_id` | `uuid` |  |
| `dataset_name` | `text` |  |
| `document_id` | `uuid` |  Nullable |
| `document_name` | `text` |  |
| `data_source_type` | `text` |  Nullable |
| `segment_id` | `uuid` |  Nullable |
| `score` | `float8` |  Nullable |
| `content` | `text` |  |
| `hit_count` | `int4` |  Nullable |
| `word_count` | `int4` |  Nullable |
| `segment_position` | `int4` |  Nullable |
| `index_node_hash` | `text` |  Nullable |
| `retriever_from` | `text` |  |
| `created_by` | `uuid` |  |
| `created_at` | `timestamp` |  |

## Table `datasets`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `tenant_id` | `uuid` |  |
| `name` | `varchar` |  |
| `description` | `text` |  Nullable |
| `provider` | `varchar` |  |
| `permission` | `varchar` |  |
| `data_source_type` | `varchar` |  Nullable |
| `indexing_technique` | `varchar` |  Nullable |
| `index_struct` | `text` |  Nullable |
| `created_by` | `uuid` |  |
| `created_at` | `timestamp` |  |
| `updated_by` | `uuid` |  Nullable |
| `updated_at` | `timestamp` |  |
| `embedding_model` | `varchar` |  Nullable |
| `embedding_model_provider` | `varchar` |  Nullable |
| `collection_binding_id` | `uuid` |  Nullable |
| `retrieval_model` | `jsonb` |  Nullable |
| `built_in_field_enabled` | `bool` |  |
| `keyword_number` | `int4` |  Nullable |
| `icon_info` | `jsonb` |  Nullable |
| `runtime_mode` | `varchar` |  Nullable |
| `pipeline_id` | `uuid` |  Nullable |
| `chunk_structure` | `varchar` |  Nullable |
| `enable_api` | `bool` |  |
| `is_multimodal` | `bool` |  |
| `summary_index_setting` | `jsonb` |  Nullable |

## Table `datasource_oauth_params`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `plugin_id` | `varchar` |  |
| `provider` | `varchar` |  |
| `system_credentials` | `jsonb` |  |

## Table `datasource_oauth_tenant_params`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `tenant_id` | `uuid` |  |
| `provider` | `varchar` |  |
| `plugin_id` | `varchar` |  |
| `client_params` | `jsonb` |  |
| `enabled` | `bool` |  |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |

## Table `datasource_providers`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `tenant_id` | `uuid` |  |
| `name` | `varchar` |  |
| `provider` | `varchar` |  |
| `plugin_id` | `varchar` |  |
| `auth_type` | `varchar` |  |
| `encrypted_credentials` | `jsonb` |  |
| `avatar_url` | `text` |  Nullable |
| `is_default` | `bool` |  |
| `expires_at` | `int4` |  |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |

## Table `dify_setups`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `version` | `varchar` | Primary |
| `setup_at` | `timestamp` |  |

## Table `document_pipeline_execution_logs`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `pipeline_id` | `uuid` |  |
| `document_id` | `uuid` |  |
| `datasource_type` | `varchar` |  |
| `datasource_info` | `text` |  |
| `datasource_node_id` | `varchar` |  |
| `input_data` | `json` |  |
| `created_by` | `uuid` |  Nullable |
| `created_at` | `timestamp` |  |

## Table `document_segment_summaries`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `dataset_id` | `uuid` |  |
| `document_id` | `uuid` |  |
| `chunk_id` | `uuid` |  |
| `summary_content` | `text` |  Nullable |
| `summary_index_node_id` | `varchar` |  Nullable |
| `summary_index_node_hash` | `varchar` |  Nullable |
| `tokens` | `int4` |  Nullable |
| `status` | `varchar` |  |
| `error` | `text` |  Nullable |
| `enabled` | `bool` |  |
| `disabled_at` | `timestamp` |  Nullable |
| `disabled_by` | `uuid` |  Nullable |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |

## Table `document_segments`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `tenant_id` | `uuid` |  |
| `dataset_id` | `uuid` |  |
| `document_id` | `uuid` |  |
| `position` | `int4` |  |
| `content` | `text` |  |
| `word_count` | `int4` |  |
| `tokens` | `int4` |  |
| `keywords` | `json` |  Nullable |
| `index_node_id` | `varchar` |  Nullable |
| `index_node_hash` | `varchar` |  Nullable |
| `hit_count` | `int4` |  |
| `enabled` | `bool` |  |
| `disabled_at` | `timestamp` |  Nullable |
| `disabled_by` | `uuid` |  Nullable |
| `status` | `varchar` |  |
| `created_by` | `uuid` |  |
| `created_at` | `timestamp` |  |
| `indexing_at` | `timestamp` |  Nullable |
| `completed_at` | `timestamp` |  Nullable |
| `error` | `text` |  Nullable |
| `stopped_at` | `timestamp` |  Nullable |
| `answer` | `text` |  Nullable |
| `updated_by` | `uuid` |  Nullable |
| `updated_at` | `timestamp` |  |

## Table `documents`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `tenant_id` | `uuid` |  |
| `dataset_id` | `uuid` |  |
| `position` | `int4` |  |
| `data_source_type` | `varchar` |  |
| `data_source_info` | `text` |  Nullable |
| `dataset_process_rule_id` | `uuid` |  Nullable |
| `batch` | `varchar` |  |
| `name` | `varchar` |  |
| `created_from` | `varchar` |  |
| `created_by` | `uuid` |  |
| `created_api_request_id` | `uuid` |  Nullable |
| `created_at` | `timestamp` |  |
| `processing_started_at` | `timestamp` |  Nullable |
| `file_id` | `text` |  Nullable |
| `word_count` | `int4` |  Nullable |
| `parsing_completed_at` | `timestamp` |  Nullable |
| `cleaning_completed_at` | `timestamp` |  Nullable |
| `splitting_completed_at` | `timestamp` |  Nullable |
| `tokens` | `int4` |  Nullable |
| `indexing_latency` | `float8` |  Nullable |
| `completed_at` | `timestamp` |  Nullable |
| `is_paused` | `bool` |  Nullable |
| `paused_by` | `uuid` |  Nullable |
| `paused_at` | `timestamp` |  Nullable |
| `error` | `text` |  Nullable |
| `stopped_at` | `timestamp` |  Nullable |
| `indexing_status` | `varchar` |  |
| `enabled` | `bool` |  |
| `disabled_at` | `timestamp` |  Nullable |
| `disabled_by` | `uuid` |  Nullable |
| `archived` | `bool` |  |
| `archived_reason` | `varchar` |  Nullable |
| `archived_by` | `uuid` |  Nullable |
| `archived_at` | `timestamp` |  Nullable |
| `updated_at` | `timestamp` |  |
| `doc_type` | `varchar` |  Nullable |
| `doc_metadata` | `jsonb` |  Nullable |
| `doc_form` | `varchar` |  |
| `doc_language` | `varchar` |  Nullable |
| `need_summary` | `bool` |  |

## Table `embeddings`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `hash` | `varchar` |  |
| `embedding` | `bytea` |  |
| `created_at` | `timestamp` |  |
| `model_name` | `varchar` |  |
| `provider_name` | `varchar` |  |

## Table `end_users`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `tenant_id` | `uuid` |  |
| `app_id` | `uuid` |  Nullable |
| `type` | `varchar` |  |
| `external_user_id` | `varchar` |  Nullable |
| `name` | `varchar` |  Nullable |
| `is_anonymous` | `bool` |  |
| `session_id` | `varchar` |  |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |

## Table `execution_extra_contents`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `type` | `varchar` |  |
| `workflow_run_id` | `uuid` |  |
| `message_id` | `uuid` |  Nullable |
| `form_id` | `uuid` |  Nullable |

## Table `exporle_banners`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `content` | `json` |  |
| `link` | `varchar` |  |
| `sort` | `int4` |  |
| `status` | `varchar` |  |
| `created_at` | `timestamp` |  |
| `language` | `varchar` |  |

## Table `external_knowledge_apis`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `name` | `varchar` |  |
| `description` | `varchar` |  |
| `tenant_id` | `uuid` |  |
| `settings` | `text` |  Nullable |
| `created_by` | `uuid` |  |
| `created_at` | `timestamp` |  |
| `updated_by` | `uuid` |  Nullable |
| `updated_at` | `timestamp` |  |

## Table `external_knowledge_bindings`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `tenant_id` | `uuid` |  |
| `external_knowledge_api_id` | `uuid` |  |
| `dataset_id` | `uuid` |  |
| `external_knowledge_id` | `varchar` |  |
| `created_by` | `uuid` |  |
| `created_at` | `timestamp` |  |
| `updated_by` | `uuid` |  Nullable |
| `updated_at` | `timestamp` |  |

## Table `human_input_form_deliveries`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `form_id` | `uuid` |  |
| `delivery_method_type` | `varchar` |  |
| `delivery_config_id` | `uuid` |  Nullable |
| `channel_payload` | `text` |  |

## Table `human_input_form_recipients`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `form_id` | `uuid` |  |
| `delivery_id` | `uuid` |  |
| `recipient_type` | `varchar` |  |
| `recipient_payload` | `text` |  |
| `access_token` | `varchar` |  Unique |

## Table `human_input_forms`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `tenant_id` | `uuid` |  |
| `app_id` | `uuid` |  |
| `workflow_run_id` | `uuid` |  Nullable |
| `form_kind` | `varchar` |  |
| `node_id` | `varchar` |  |
| `form_definition` | `text` |  |
| `rendered_content` | `text` |  |
| `status` | `varchar` |  |
| `expiration_time` | `timestamp` |  |
| `selected_action_id` | `varchar` |  Nullable |
| `submitted_data` | `text` |  Nullable |
| `submitted_at` | `timestamp` |  Nullable |
| `submission_user_id` | `uuid` |  Nullable |
| `submission_end_user_id` | `uuid` |  Nullable |
| `completed_by_recipient_id` | `uuid` |  Nullable |

## Table `installed_apps`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `tenant_id` | `uuid` |  |
| `app_id` | `uuid` |  |
| `app_owner_tenant_id` | `uuid` |  |
| `position` | `int4` |  |
| `is_pinned` | `bool` |  |
| `last_used_at` | `timestamp` |  Nullable |
| `created_at` | `timestamp` |  |

## Table `invitation_codes`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `int4` | Primary |
| `batch` | `varchar` |  |
| `code` | `varchar` |  |
| `status` | `varchar` |  |
| `used_at` | `timestamp` |  Nullable |
| `used_by_tenant_id` | `uuid` |  Nullable |
| `used_by_account_id` | `uuid` |  Nullable |
| `deprecated_at` | `timestamp` |  Nullable |
| `created_at` | `timestamp` |  |

## Table `load_balancing_model_configs`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `tenant_id` | `uuid` |  |
| `provider_name` | `varchar` |  |
| `model_name` | `varchar` |  |
| `model_type` | `varchar` |  |
| `name` | `varchar` |  |
| `encrypted_config` | `text` |  Nullable |
| `enabled` | `bool` |  |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `credential_id` | `uuid` |  Nullable |
| `credential_source_type` | `varchar` |  Nullable |

## Table `message_agent_thoughts`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `message_id` | `uuid` |  |
| `message_chain_id` | `uuid` |  Nullable |
| `position` | `int4` |  |
| `thought` | `text` |  Nullable |
| `tool` | `text` |  Nullable |
| `tool_input` | `text` |  Nullable |
| `observation` | `text` |  Nullable |
| `tool_process_data` | `text` |  Nullable |
| `message` | `text` |  Nullable |
| `message_token` | `int4` |  Nullable |
| `message_unit_price` | `numeric` |  Nullable |
| `answer` | `text` |  Nullable |
| `answer_token` | `int4` |  Nullable |
| `answer_unit_price` | `numeric` |  Nullable |
| `tokens` | `int4` |  Nullable |
| `total_price` | `numeric` |  Nullable |
| `currency` | `varchar` |  Nullable |
| `latency` | `float8` |  Nullable |
| `created_by_role` | `varchar` |  |
| `created_by` | `uuid` |  |
| `created_at` | `timestamp` |  |
| `message_price_unit` | `numeric` |  |
| `answer_price_unit` | `numeric` |  |
| `message_files` | `text` |  Nullable |
| `tool_labels_str` | `text` |  |
| `tool_meta_str` | `text` |  |

## Table `message_annotations`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `app_id` | `uuid` |  |
| `conversation_id` | `uuid` |  Nullable |
| `message_id` | `uuid` |  Nullable |
| `content` | `text` |  |
| `account_id` | `uuid` |  |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `question` | `text` |  |
| `hit_count` | `int4` |  |

## Table `message_chains`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `message_id` | `uuid` |  |
| `type` | `varchar` |  |
| `input` | `text` |  Nullable |
| `output` | `text` |  Nullable |
| `created_at` | `timestamp` |  |

## Table `message_feedbacks`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `app_id` | `uuid` |  |
| `conversation_id` | `uuid` |  |
| `message_id` | `uuid` |  |
| `rating` | `varchar` |  |
| `content` | `text` |  Nullable |
| `from_source` | `varchar` |  |
| `from_end_user_id` | `uuid` |  Nullable |
| `from_account_id` | `uuid` |  Nullable |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |

## Table `message_files`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `message_id` | `uuid` |  |
| `type` | `varchar` |  |
| `transfer_method` | `varchar` |  |
| `url` | `text` |  Nullable |
| `upload_file_id` | `uuid` |  Nullable |
| `created_by_role` | `varchar` |  |
| `created_by` | `uuid` |  |
| `created_at` | `timestamp` |  |
| `belongs_to` | `varchar` |  Nullable |

## Table `messages`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `app_id` | `uuid` |  |
| `model_provider` | `varchar` |  Nullable |
| `model_id` | `varchar` |  Nullable |
| `override_model_configs` | `text` |  Nullable |
| `conversation_id` | `uuid` |  |
| `inputs` | `json` |  |
| `query` | `text` |  |
| `message` | `json` |  |
| `message_tokens` | `int4` |  |
| `message_unit_price` | `numeric` |  |
| `answer` | `text` |  |
| `answer_tokens` | `int4` |  |
| `answer_unit_price` | `numeric` |  |
| `provider_response_latency` | `float8` |  |
| `total_price` | `numeric` |  Nullable |
| `currency` | `varchar` |  |
| `from_source` | `varchar` |  |
| `from_end_user_id` | `uuid` |  Nullable |
| `from_account_id` | `uuid` |  Nullable |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `agent_based` | `bool` |  |
| `message_price_unit` | `numeric` |  |
| `answer_price_unit` | `numeric` |  |
| `workflow_run_id` | `uuid` |  Nullable |
| `status` | `varchar` |  |
| `error` | `text` |  Nullable |
| `message_metadata` | `text` |  Nullable |
| `invoke_from` | `varchar` |  Nullable |
| `parent_message_id` | `uuid` |  Nullable |
| `app_mode` | `varchar` |  Nullable |

## Table `oauth_provider_apps`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `app_icon` | `varchar` |  |
| `app_label` | `json` |  |
| `client_id` | `varchar` |  |
| `client_secret` | `varchar` |  |
| `redirect_uris` | `json` |  |
| `scope` | `varchar` |  |
| `created_at` | `timestamp` |  |

## Table `operation_logs`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `tenant_id` | `uuid` |  |
| `account_id` | `uuid` |  |
| `action` | `varchar` |  |
| `content` | `json` |  Nullable |
| `created_at` | `timestamp` |  |
| `created_ip` | `varchar` |  |
| `updated_at` | `timestamp` |  |

## Table `pinned_conversations`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `app_id` | `uuid` |  |
| `conversation_id` | `uuid` |  |
| `created_by` | `uuid` |  |
| `created_at` | `timestamp` |  |
| `created_by_role` | `varchar` |  |

## Table `pipeline_built_in_templates`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `name` | `varchar` |  |
| `description` | `text` |  |
| `chunk_structure` | `varchar` |  |
| `icon` | `json` |  |
| `yaml_content` | `text` |  |
| `copyright` | `varchar` |  |
| `privacy_policy` | `varchar` |  |
| `position` | `int4` |  |
| `install_count` | `int4` |  |
| `language` | `varchar` |  |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |

## Table `pipeline_customized_templates`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `tenant_id` | `uuid` |  |
| `name` | `varchar` |  |
| `description` | `text` |  |
| `chunk_structure` | `varchar` |  |
| `icon` | `json` |  |
| `position` | `int4` |  |
| `yaml_content` | `text` |  |
| `install_count` | `int4` |  |
| `language` | `varchar` |  |
| `created_by` | `uuid` |  |
| `updated_by` | `uuid` |  Nullable |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |

## Table `pipeline_recommended_plugins`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `plugin_id` | `text` |  |
| `provider_name` | `text` |  |
| `position` | `int4` |  |
| `active` | `bool` |  |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `type` | `varchar` |  |

## Table `pipelines`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `tenant_id` | `uuid` |  |
| `name` | `varchar` |  |
| `description` | `text` |  |
| `workflow_id` | `uuid` |  Nullable |
| `is_public` | `bool` |  |
| `is_published` | `bool` |  |
| `created_by` | `uuid` |  Nullable |
| `created_at` | `timestamp` |  |
| `updated_by` | `uuid` |  Nullable |
| `updated_at` | `timestamp` |  |

## Table `provider_credentials`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `tenant_id` | `uuid` |  |
| `provider_name` | `varchar` |  |
| `credential_name` | `varchar` |  |
| `encrypted_config` | `text` |  |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |

## Table `provider_model_credentials`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `tenant_id` | `uuid` |  |
| `provider_name` | `varchar` |  |
| `model_name` | `varchar` |  |
| `model_type` | `varchar` |  |
| `credential_name` | `varchar` |  |
| `encrypted_config` | `text` |  |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |

## Table `provider_model_settings`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `tenant_id` | `uuid` |  |
| `provider_name` | `varchar` |  |
| `model_name` | `varchar` |  |
| `model_type` | `varchar` |  |
| `enabled` | `bool` |  |
| `load_balancing_enabled` | `bool` |  |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |

## Table `provider_models`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `tenant_id` | `uuid` |  |
| `provider_name` | `varchar` |  |
| `model_name` | `varchar` |  |
| `model_type` | `varchar` |  |
| `is_valid` | `bool` |  |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `credential_id` | `uuid` |  Nullable |

## Table `provider_orders`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `tenant_id` | `uuid` |  |
| `provider_name` | `varchar` |  |
| `account_id` | `uuid` |  |
| `payment_product_id` | `varchar` |  |
| `payment_id` | `varchar` |  Nullable |
| `transaction_id` | `varchar` |  Nullable |
| `quantity` | `int4` |  |
| `currency` | `varchar` |  Nullable |
| `total_amount` | `int4` |  Nullable |
| `payment_status` | `varchar` |  |
| `paid_at` | `timestamp` |  Nullable |
| `pay_failed_at` | `timestamp` |  Nullable |
| `refunded_at` | `timestamp` |  Nullable |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |

## Table `providers`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `tenant_id` | `uuid` |  |
| `provider_name` | `varchar` |  |
| `provider_type` | `varchar` |  |
| `is_valid` | `bool` |  |
| `last_used` | `timestamp` |  Nullable |
| `quota_type` | `varchar` |  Nullable |
| `quota_limit` | `int8` |  Nullable |
| `quota_used` | `int8` |  Nullable |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `credential_id` | `uuid` |  Nullable |

## Table `rate_limit_logs`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `tenant_id` | `uuid` |  |
| `subscription_plan` | `varchar` |  |
| `operation` | `varchar` |  |
| `created_at` | `timestamp` |  |

## Table `recommended_apps`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `app_id` | `uuid` |  |
| `description` | `json` |  |
| `copyright` | `varchar` |  |
| `privacy_policy` | `varchar` |  |
| `category` | `varchar` |  |
| `position` | `int4` |  |
| `is_listed` | `bool` |  |
| `install_count` | `int4` |  |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `language` | `varchar` |  |
| `custom_disclaimer` | `text` |  |

## Table `saved_messages`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `app_id` | `uuid` |  |
| `message_id` | `uuid` |  |
| `created_by` | `uuid` |  |
| `created_at` | `timestamp` |  |
| `created_by_role` | `varchar` |  |

## Table `segment_attachment_bindings`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `tenant_id` | `uuid` |  |
| `dataset_id` | `uuid` |  |
| `document_id` | `uuid` |  |
| `segment_id` | `uuid` |  |
| `attachment_id` | `uuid` |  |
| `created_at` | `timestamp` |  |

## Table `sites`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `app_id` | `uuid` |  |
| `title` | `varchar` |  |
| `icon` | `varchar` |  Nullable |
| `icon_background` | `varchar` |  Nullable |
| `description` | `text` |  Nullable |
| `default_language` | `varchar` |  |
| `copyright` | `varchar` |  Nullable |
| `privacy_policy` | `varchar` |  Nullable |
| `customize_domain` | `varchar` |  Nullable |
| `customize_token_strategy` | `varchar` |  |
| `prompt_public` | `bool` |  |
| `status` | `varchar` |  |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `code` | `varchar` |  Nullable |
| `custom_disclaimer` | `text` |  |
| `show_workflow_steps` | `bool` |  |
| `chat_color_theme` | `varchar` |  Nullable |
| `chat_color_theme_inverted` | `bool` |  |
| `icon_type` | `varchar` |  Nullable |
| `created_by` | `uuid` |  Nullable |
| `updated_by` | `uuid` |  Nullable |
| `use_icon_as_answer_icon` | `bool` |  |

## Table `tag_bindings`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `tenant_id` | `uuid` |  Nullable |
| `tag_id` | `uuid` |  Nullable |
| `target_id` | `uuid` |  Nullable |
| `created_by` | `uuid` |  |
| `created_at` | `timestamp` |  |

## Table `tags`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `tenant_id` | `uuid` |  Nullable |
| `type` | `varchar` |  |
| `name` | `varchar` |  |
| `created_by` | `uuid` |  |
| `created_at` | `timestamp` |  |

## Table `tenant_account_joins`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `tenant_id` | `uuid` |  |
| `account_id` | `uuid` |  |
| `role` | `varchar` |  |
| `invited_by` | `uuid` |  Nullable |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `current` | `bool` |  |

## Table `tenant_credit_pools`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `tenant_id` | `uuid` |  |
| `pool_type` | `varchar` |  |
| `quota_limit` | `int8` |  |
| `quota_used` | `int8` |  |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |

## Table `tenant_default_models`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `tenant_id` | `uuid` |  |
| `provider_name` | `varchar` |  |
| `model_name` | `varchar` |  |
| `model_type` | `varchar` |  |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |

## Table `tenant_plugin_auto_upgrade_strategies`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `tenant_id` | `uuid` |  Unique |
| `strategy_setting` | `varchar` |  |
| `upgrade_time_of_day` | `int4` |  |
| `upgrade_mode` | `varchar` |  |
| `exclude_plugins` | `json` |  |
| `include_plugins` | `json` |  |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |

## Table `tenant_preferred_model_providers`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `tenant_id` | `uuid` |  |
| `provider_name` | `varchar` |  |
| `preferred_provider_type` | `varchar` |  |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |

## Table `tenants`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `name` | `varchar` |  |
| `encrypt_public_key` | `text` |  Nullable |
| `plan` | `varchar` |  |
| `status` | `varchar` |  |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `custom_config` | `text` |  Nullable |

## Table `tidb_auth_bindings`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `tenant_id` | `uuid` |  Nullable |
| `cluster_id` | `varchar` |  |
| `cluster_name` | `varchar` |  |
| `active` | `bool` |  |
| `status` | `varchar` |  |
| `account` | `varchar` |  |
| `password` | `varchar` |  |
| `created_at` | `timestamp` |  |
| `qdrant_endpoint` | `varchar` |  Nullable |

## Table `tool_api_providers`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `name` | `varchar` |  |
| `schema` | `text` |  |
| `schema_type_str` | `varchar` |  |
| `user_id` | `uuid` |  |
| `tenant_id` | `uuid` |  |
| `tools_str` | `text` |  |
| `icon` | `varchar` |  |
| `credentials_str` | `text` |  |
| `description` | `text` |  |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `privacy_policy` | `varchar` |  Nullable |
| `custom_disclaimer` | `text` |  |

## Table `tool_builtin_providers`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `tenant_id` | `uuid` |  Nullable |
| `user_id` | `uuid` |  |
| `provider` | `varchar` |  |
| `encrypted_credentials` | `text` |  Nullable |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `name` | `varchar` |  |
| `is_default` | `bool` |  |
| `credential_type` | `varchar` |  |
| `expires_at` | `int8` |  |

## Table `tool_conversation_variables`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `user_id` | `uuid` |  |
| `tenant_id` | `uuid` |  |
| `conversation_id` | `uuid` |  |
| `variables_str` | `text` |  |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |

## Table `tool_files`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `user_id` | `uuid` |  |
| `tenant_id` | `uuid` |  |
| `conversation_id` | `uuid` |  Nullable |
| `file_key` | `varchar` |  |
| `mimetype` | `varchar` |  |
| `original_url` | `varchar` |  Nullable |
| `name` | `varchar` |  |
| `size` | `int4` |  |

## Table `tool_label_bindings`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `tool_id` | `varchar` |  |
| `tool_type` | `varchar` |  |
| `label_name` | `varchar` |  |

## Table `tool_mcp_providers`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `name` | `varchar` |  |
| `server_identifier` | `varchar` |  |
| `server_url` | `text` |  |
| `server_url_hash` | `varchar` |  |
| `icon` | `varchar` |  Nullable |
| `tenant_id` | `uuid` |  |
| `user_id` | `uuid` |  |
| `encrypted_credentials` | `text` |  Nullable |
| `authed` | `bool` |  |
| `tools` | `text` |  |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `timeout` | `float8` |  |
| `sse_read_timeout` | `float8` |  |
| `encrypted_headers` | `text` |  Nullable |

## Table `tool_model_invokes`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `user_id` | `uuid` |  |
| `tenant_id` | `uuid` |  |
| `provider` | `varchar` |  |
| `tool_type` | `varchar` |  |
| `tool_name` | `varchar` |  |
| `model_parameters` | `text` |  |
| `prompt_messages` | `text` |  |
| `model_response` | `text` |  |
| `prompt_tokens` | `int4` |  |
| `answer_tokens` | `int4` |  |
| `answer_unit_price` | `numeric` |  |
| `answer_price_unit` | `numeric` |  |
| `provider_response_latency` | `float8` |  |
| `total_price` | `numeric` |  Nullable |
| `currency` | `varchar` |  |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |

## Table `tool_oauth_system_clients`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `plugin_id` | `varchar` |  |
| `provider` | `varchar` |  |
| `encrypted_oauth_params` | `text` |  |

## Table `tool_oauth_tenant_clients`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `tenant_id` | `uuid` |  |
| `plugin_id` | `varchar` |  |
| `provider` | `varchar` |  |
| `enabled` | `bool` |  |
| `encrypted_oauth_params` | `text` |  |

## Table `tool_published_apps`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `app_id` | `uuid` |  |
| `user_id` | `uuid` |  |
| `description` | `text` |  |
| `llm_description` | `text` |  |
| `query_description` | `text` |  |
| `query_name` | `varchar` |  |
| `tool_name` | `varchar` |  |
| `author` | `varchar` |  |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |

## Table `tool_workflow_providers`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `name` | `varchar` |  |
| `icon` | `varchar` |  |
| `app_id` | `uuid` |  |
| `user_id` | `uuid` |  |
| `tenant_id` | `uuid` |  |
| `description` | `text` |  |
| `parameter_configuration` | `text` |  |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `privacy_policy` | `varchar` |  Nullable |
| `version` | `varchar` |  |
| `label` | `varchar` |  |

## Table `trace_app_config`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `app_id` | `uuid` |  |
| `tracing_provider` | `varchar` |  Nullable |
| `tracing_config` | `json` |  Nullable |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `is_active` | `bool` |  |

## Table `trial_apps`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `app_id` | `uuid` |  Unique |
| `tenant_id` | `uuid` |  |
| `created_at` | `timestamp` |  |
| `trial_limit` | `int4` |  |

## Table `trigger_oauth_system_clients`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `plugin_id` | `varchar` |  |
| `provider` | `varchar` |  |
| `encrypted_oauth_params` | `text` |  |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |

## Table `trigger_oauth_tenant_clients`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `tenant_id` | `uuid` |  |
| `plugin_id` | `varchar` |  |
| `provider` | `varchar` |  |
| `enabled` | `bool` |  |
| `encrypted_oauth_params` | `text` |  |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |

## Table `trigger_subscriptions`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `name` | `varchar` |  |
| `tenant_id` | `uuid` |  |
| `user_id` | `uuid` |  |
| `provider_id` | `varchar` |  |
| `endpoint_id` | `varchar` |  |
| `parameters` | `json` |  |
| `properties` | `json` |  |
| `credentials` | `json` |  |
| `credential_type` | `varchar` |  |
| `credential_expires_at` | `int4` |  |
| `expires_at` | `int4` |  |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |

## Table `upload_files`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `tenant_id` | `uuid` |  |
| `storage_type` | `varchar` |  |
| `key` | `varchar` |  |
| `name` | `varchar` |  |
| `size` | `int4` |  |
| `extension` | `varchar` |  |
| `mime_type` | `varchar` |  Nullable |
| `created_by` | `uuid` |  |
| `created_at` | `timestamp` |  |
| `used` | `bool` |  |
| `used_by` | `uuid` |  Nullable |
| `used_at` | `timestamp` |  Nullable |
| `hash` | `varchar` |  Nullable |
| `created_by_role` | `varchar` |  |
| `source_url` | `text` |  |

## Table `whitelists`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `tenant_id` | `uuid` |  Nullable |
| `category` | `varchar` |  |
| `created_at` | `timestamp` |  |

## Table `workflow_app_logs`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `tenant_id` | `uuid` |  |
| `app_id` | `uuid` |  |
| `workflow_id` | `uuid` |  |
| `workflow_run_id` | `uuid` |  |
| `created_from` | `varchar` |  |
| `created_by_role` | `varchar` |  |
| `created_by` | `uuid` |  |
| `created_at` | `timestamp` |  |

## Table `workflow_archive_logs`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `log_id` | `uuid` |  Nullable |
| `tenant_id` | `uuid` |  |
| `app_id` | `uuid` |  |
| `workflow_id` | `uuid` |  |
| `workflow_run_id` | `uuid` |  |
| `created_by_role` | `varchar` |  |
| `created_by` | `uuid` |  |
| `log_created_at` | `timestamp` |  Nullable |
| `log_created_from` | `varchar` |  Nullable |
| `run_version` | `varchar` |  |
| `run_status` | `varchar` |  |
| `run_triggered_from` | `varchar` |  |
| `run_error` | `text` |  Nullable |
| `run_elapsed_time` | `float8` |  |
| `run_total_tokens` | `int8` |  |
| `run_total_steps` | `int4` |  Nullable |
| `run_created_at` | `timestamp` |  |
| `run_finished_at` | `timestamp` |  Nullable |
| `run_exceptions_count` | `int4` |  Nullable |
| `trigger_metadata` | `text` |  Nullable |
| `archived_at` | `timestamp` |  |

## Table `workflow_comment_mentions`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `comment_id` | `uuid` |  |
| `reply_id` | `uuid` |  Nullable |
| `mentioned_user_id` | `uuid` |  |

## Table `workflow_comment_replies`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `comment_id` | `uuid` |  |
| `content` | `text` |  |
| `created_by` | `uuid` |  |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |

## Table `workflow_comments`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `tenant_id` | `uuid` |  |
| `app_id` | `uuid` |  |
| `position_x` | `float8` |  |
| `position_y` | `float8` |  |
| `content` | `text` |  |
| `created_by` | `uuid` |  |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `resolved` | `bool` |  |
| `resolved_at` | `timestamp` |  Nullable |
| `resolved_by` | `uuid` |  Nullable |

## Table `workflow_conversation_variables`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `conversation_id` | `uuid` | Primary |
| `app_id` | `uuid` |  |
| `data` | `text` |  |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |

## Table `workflow_draft_variable_files`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `created_at` | `timestamp` |  |
| `tenant_id` | `uuid` |  |
| `app_id` | `uuid` |  |
| `user_id` | `uuid` |  |
| `upload_file_id` | `uuid` |  |
| `size` | `int8` |  |
| `length` | `int4` |  Nullable |
| `value_type` | `varchar` |  |

## Table `workflow_draft_variables`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `app_id` | `uuid` |  |
| `last_edited_at` | `timestamp` |  Nullable |
| `node_id` | `varchar` |  |
| `name` | `varchar` |  |
| `description` | `varchar` |  |
| `selector` | `varchar` |  |
| `value_type` | `varchar` |  |
| `value` | `text` |  |
| `visible` | `bool` |  |
| `editable` | `bool` |  |
| `node_execution_id` | `uuid` |  Nullable |
| `file_id` | `uuid` |  Nullable |
| `is_default_value` | `bool` |  |
| `user_id` | `uuid` |  Nullable |

## Table `workflow_node_execution_offload`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `created_at` | `timestamp` |  |
| `tenant_id` | `uuid` |  |
| `app_id` | `uuid` |  |
| `node_execution_id` | `uuid` |  Nullable |
| `type` | `varchar` |  |
| `file_id` | `uuid` |  |

## Table `workflow_node_executions`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `tenant_id` | `uuid` |  |
| `app_id` | `uuid` |  |
| `workflow_id` | `uuid` |  |
| `triggered_from` | `varchar` |  |
| `workflow_run_id` | `uuid` |  Nullable |
| `index` | `int4` |  |
| `predecessor_node_id` | `varchar` |  Nullable |
| `node_id` | `varchar` |  |
| `node_type` | `varchar` |  |
| `title` | `varchar` |  |
| `inputs` | `text` |  Nullable |
| `process_data` | `text` |  Nullable |
| `outputs` | `text` |  Nullable |
| `status` | `varchar` |  |
| `error` | `text` |  Nullable |
| `elapsed_time` | `float8` |  |
| `execution_metadata` | `text` |  Nullable |
| `created_at` | `timestamp` |  |
| `created_by_role` | `varchar` |  |
| `created_by` | `uuid` |  |
| `finished_at` | `timestamp` |  Nullable |
| `node_execution_id` | `varchar` |  Nullable |

## Table `workflow_pause_reasons`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `pause_id` | `uuid` |  |
| `type_` | `varchar` |  |
| `form_id` | `varchar` |  |
| `node_id` | `varchar` |  |
| `message` | `varchar` |  |

## Table `workflow_pauses`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `workflow_id` | `uuid` |  |
| `workflow_run_id` | `uuid` |  Unique |
| `resumed_at` | `timestamp` |  Nullable |
| `state_object_key` | `varchar` |  |
| `id` | `uuid` | Primary |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |

## Table `workflow_plugin_triggers`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `app_id` | `uuid` |  |
| `node_id` | `varchar` |  |
| `tenant_id` | `uuid` |  |
| `provider_id` | `varchar` |  |
| `event_name` | `varchar` |  |
| `subscription_id` | `varchar` |  |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |

## Table `workflow_runs`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `tenant_id` | `uuid` |  |
| `app_id` | `uuid` |  |
| `workflow_id` | `uuid` |  |
| `type` | `varchar` |  |
| `triggered_from` | `varchar` |  |
| `version` | `varchar` |  |
| `graph` | `text` |  Nullable |
| `inputs` | `text` |  Nullable |
| `status` | `varchar` |  |
| `outputs` | `text` |  Nullable |
| `error` | `text` |  Nullable |
| `elapsed_time` | `float8` |  |
| `total_tokens` | `int8` |  |
| `total_steps` | `int4` |  Nullable |
| `created_by_role` | `varchar` |  |
| `created_by` | `uuid` |  |
| `created_at` | `timestamp` |  |
| `finished_at` | `timestamp` |  Nullable |
| `exceptions_count` | `int4` |  Nullable |

## Table `workflow_schedule_plans`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `app_id` | `uuid` |  |
| `node_id` | `varchar` |  |
| `tenant_id` | `uuid` |  |
| `cron_expression` | `varchar` |  |
| `timezone` | `varchar` |  |
| `next_run_at` | `timestamp` |  Nullable |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |

## Table `workflow_trigger_logs`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `tenant_id` | `uuid` |  |
| `app_id` | `uuid` |  |
| `workflow_id` | `uuid` |  |
| `workflow_run_id` | `uuid` |  Nullable |
| `root_node_id` | `varchar` |  Nullable |
| `trigger_metadata` | `text` |  |
| `trigger_type` | `varchar` |  |
| `trigger_data` | `text` |  |
| `inputs` | `text` |  |
| `outputs` | `text` |  Nullable |
| `status` | `varchar` |  |
| `error` | `text` |  Nullable |
| `queue_name` | `varchar` |  |
| `celery_task_id` | `varchar` |  Nullable |
| `retry_count` | `int4` |  |
| `elapsed_time` | `float8` |  Nullable |
| `total_tokens` | `int4` |  Nullable |
| `created_at` | `timestamp` |  |
| `created_by_role` | `varchar` |  |
| `created_by` | `varchar` |  |
| `triggered_at` | `timestamp` |  Nullable |
| `finished_at` | `timestamp` |  Nullable |

## Table `workflow_webhook_triggers`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `app_id` | `uuid` |  |
| `node_id` | `varchar` |  |
| `tenant_id` | `uuid` |  |
| `webhook_id` | `varchar` |  Unique |
| `created_by` | `uuid` |  |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |

## Table `workflows`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `tenant_id` | `uuid` |  |
| `app_id` | `uuid` |  |
| `type` | `varchar` |  |
| `version` | `varchar` |  |
| `graph` | `text` |  |
| `features` | `text` |  |
| `created_by` | `uuid` |  |
| `created_at` | `timestamp` |  |
| `updated_by` | `uuid` |  Nullable |
| `updated_at` | `timestamp` |  |
| `environment_variables` | `text` |  |
| `conversation_variables` | `text` |  |
| `marked_name` | `varchar` |  |
| `marked_comment` | `varchar` |  |
| `rag_pipeline_variables` | `text` |  |

