## Table `_typeorm_generated_columns_and_materialized_views`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `type` | `varchar` |  |
| `database` | `varchar` |  Nullable |
| `schema` | `varchar` |  Nullable |
| `table` | `varchar` |  Nullable |
| `name` | `varchar` |  Nullable |
| `value` | `text` |  Nullable |

## Table `_typeorm_migrations`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `int4` | Primary |
| `timestamp` | `int8` |  |
| `name` | `varchar` |  |

## Table `agent`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `standardId` | `uuid` |  Nullable |
| `name` | `varchar` |  |
| `label` | `varchar` |  |
| `icon` | `varchar` |  Nullable |
| `description` | `varchar` |  Nullable |
| `prompt` | `text` |  |
| `modelId` | `varchar` |  |
| `responseFormat` | `jsonb` |  Nullable |
| `workspaceId` | `uuid` |  |
| `isCustom` | `bool` |  |
| `createdAt` | `timestamptz` |  |
| `updatedAt` | `timestamptz` |  |
| `deletedAt` | `timestamptz` |  Nullable |
| `applicationId` | `uuid` |  Nullable |
| `modelConfiguration` | `jsonb` |  Nullable |
| `universalIdentifier` | `uuid` |  Nullable |

## Table `agentChatMessage`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `threadId` | `uuid` |  |
| `role` | `agentChatMessage_role_enum` |  |
| `createdAt` | `timestamp` |  |

## Table `agentChatMessagePart`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `messageId` | `uuid` |  |
| `orderIndex` | `int4` |  |
| `type` | `varchar` |  |
| `textContent` | `text` |  Nullable |
| `reasoningContent` | `text` |  Nullable |
| `toolName` | `varchar` |  Nullable |
| `toolCallId` | `varchar` |  Nullable |
| `toolInput` | `jsonb` |  Nullable |
| `toolOutput` | `jsonb` |  Nullable |
| `state` | `varchar` |  Nullable |
| `errorMessage` | `text` |  Nullable |
| `errorDetails` | `jsonb` |  Nullable |
| `sourceUrlSourceId` | `varchar` |  Nullable |
| `sourceUrlUrl` | `varchar` |  Nullable |
| `sourceUrlTitle` | `varchar` |  Nullable |
| `sourceDocumentSourceId` | `varchar` |  Nullable |
| `sourceDocumentMediaType` | `varchar` |  Nullable |
| `sourceDocumentTitle` | `varchar` |  Nullable |
| `sourceDocumentFilename` | `varchar` |  Nullable |
| `fileMediaType` | `varchar` |  Nullable |
| `fileFilename` | `varchar` |  Nullable |
| `fileUrl` | `varchar` |  Nullable |
| `providerMetadata` | `jsonb` |  Nullable |
| `createdAt` | `timestamp` |  |

## Table `agentChatThread`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `userWorkspaceId` | `uuid` |  |
| `title` | `varchar` |  Nullable |
| `createdAt` | `timestamp` |  |
| `updatedAt` | `timestamp` |  |

## Table `agentHandoff`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `fromAgentId` | `uuid` |  |
| `toAgentId` | `uuid` |  |
| `workspaceId` | `uuid` |  |
| `description` | `text` |  Nullable |
| `createdAt` | `timestamptz` |  |
| `updatedAt` | `timestamptz` |  |
| `deletedAt` | `timestamptz` |  Nullable |

## Table `apiKey`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `name` | `varchar` |  |
| `expiresAt` | `timestamptz` |  |
| `revokedAt` | `timestamptz` |  Nullable |
| `workspaceId` | `uuid` |  |
| `createdAt` | `timestamptz` |  |
| `updatedAt` | `timestamptz` |  |

## Table `appToken`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `userId` | `uuid` |  Nullable |
| `workspaceId` | `uuid` |  Nullable |
| `type` | `text` |  |
| `value` | `text` |  Nullable |
| `expiresAt` | `timestamptz` |  |
| `deletedAt` | `timestamptz` |  Nullable |
| `revokedAt` | `timestamptz` |  Nullable |
| `createdAt` | `timestamptz` |  |
| `updatedAt` | `timestamptz` |  |
| `context` | `jsonb` |  Nullable |

## Table `application`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `universalIdentifier` | `uuid` |  Nullable |
| `name` | `text` |  |
| `description` | `text` |  Nullable |
| `version` | `text` |  Nullable |
| `sourceType` | `text` |  |
| `sourcePath` | `text` |  |
| `workspaceId` | `uuid` |  |
| `createdAt` | `timestamptz` |  |
| `updatedAt` | `timestamptz` |  |
| `deletedAt` | `timestamptz` |  Nullable |
| `serverlessFunctionLayerId` | `uuid` |  |

## Table `applicationVariable`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `key` | `text` |  |
| `value` | `text` |  |
| `description` | `text` |  |
| `isSecret` | `bool` |  |
| `applicationId` | `uuid` |  Nullable |
| `createdAt` | `timestamptz` |  |
| `updatedAt` | `timestamptz` |  |

## Table `approvedAccessDomain`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `createdAt` | `timestamptz` |  |
| `updatedAt` | `timestamptz` |  |
| `domain` | `varchar` |  |
| `isValidated` | `bool` |  |
| `workspaceId` | `uuid` |  |

## Table `cronTrigger`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `universalIdentifier` | `uuid` |  Nullable |
| `id` | `uuid` | Primary |
| `settings` | `jsonb` |  |
| `workspaceId` | `uuid` |  |
| `createdAt` | `timestamptz` |  |
| `updatedAt` | `timestamptz` |  |
| `serverlessFunctionId` | `uuid` |  |
| `applicationId` | `uuid` |  Nullable |

## Table `dataSource`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `label` | `varchar` |  Nullable |
| `url` | `varchar` |  Nullable |
| `schema` | `varchar` |  Nullable |
| `type` | `dataSource_type_enum` |  |
| `isRemote` | `bool` |  |
| `workspaceId` | `uuid` |  |
| `createdAt` | `timestamptz` |  |
| `updatedAt` | `timestamptz` |  |

## Table `databaseEventTrigger`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `universalIdentifier` | `uuid` |  Nullable |
| `id` | `uuid` | Primary |
| `settings` | `jsonb` |  |
| `workspaceId` | `uuid` |  |
| `createdAt` | `timestamptz` |  |
| `updatedAt` | `timestamptz` |  |
| `serverlessFunctionId` | `uuid` |  |
| `applicationId` | `uuid` |  Nullable |

## Table `emailingDomain`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `createdAt` | `timestamptz` |  |
| `updatedAt` | `timestamptz` |  |
| `domain` | `varchar` |  |
| `driver` | `emailingDomain_driver_enum` |  |
| `status` | `emailingDomain_status_enum` |  |
| `verificationRecords` | `jsonb` |  Nullable |
| `verifiedAt` | `timestamptz` |  Nullable |
| `workspaceId` | `uuid` |  |

## Table `featureFlag`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `key` | `text` |  |
| `workspaceId` | `uuid` |  |
| `value` | `bool` |  |
| `createdAt` | `timestamptz` |  |
| `updatedAt` | `timestamptz` |  |

## Table `fieldMetadata`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `standardId` | `uuid` |  Nullable |
| `objectMetadataId` | `uuid` |  |
| `type` | `varchar` |  |
| `name` | `varchar` |  |
| `label` | `varchar` |  |
| `defaultValue` | `jsonb` |  Nullable |
| `description` | `text` |  Nullable |
| `icon` | `varchar` |  Nullable |
| `standardOverrides` | `jsonb` |  Nullable |
| `options` | `jsonb` |  Nullable |
| `settings` | `jsonb` |  Nullable |
| `isCustom` | `bool` |  |
| `isActive` | `bool` |  |
| `isSystem` | `bool` |  |
| `isUIReadOnly` | `bool` |  |
| `isNullable` | `bool` |  Nullable |
| `isUnique` | `bool` |  Nullable |
| `workspaceId` | `uuid` |  |
| `isLabelSyncedWithName` | `bool` |  |
| `relationTargetFieldMetadataId` | `uuid` |  Nullable Unique |
| `relationTargetObjectMetadataId` | `uuid` |  Nullable |
| `morphId` | `uuid` |  Nullable |
| `createdAt` | `timestamptz` |  |
| `updatedAt` | `timestamptz` |  |
| `universalIdentifier` | `uuid` |  Nullable |
| `applicationId` | `uuid` |  Nullable |

## Table `fieldPermission`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `roleId` | `uuid` |  |
| `objectMetadataId` | `uuid` |  |
| `fieldMetadataId` | `uuid` |  |
| `canReadFieldValue` | `bool` |  Nullable |
| `canUpdateFieldValue` | `bool` |  Nullable |
| `workspaceId` | `uuid` |  |
| `createdAt` | `timestamptz` |  |
| `updatedAt` | `timestamptz` |  |

## Table `file`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `name` | `varchar` |  |
| `fullPath` | `varchar` |  |
| `size` | `int8` |  |
| `type` | `varchar` |  |
| `workspaceId` | `uuid` |  |
| `createdAt` | `timestamptz` |  |

## Table `indexFieldMetadata`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `indexMetadataId` | `uuid` |  |
| `fieldMetadataId` | `uuid` |  |
| `order` | `int4` |  |
| `createdAt` | `timestamptz` |  |
| `updatedAt` | `timestamptz` |  |

## Table `indexMetadata`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `createdAt` | `timestamptz` |  |
| `updatedAt` | `timestamptz` |  |
| `name` | `varchar` |  |
| `workspaceId` | `varchar` |  Nullable |
| `objectMetadataId` | `uuid` |  |
| `isCustom` | `bool` |  |
| `isUnique` | `bool` |  |
| `indexWhereClause` | `text` |  Nullable |
| `indexType` | `indexMetadata_indextype_enum` |  |
| `universalIdentifier` | `uuid` |  Nullable |
| `applicationId` | `uuid` |  Nullable |

## Table `keyValuePair`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `userId` | `uuid` |  Nullable |
| `workspaceId` | `uuid` |  Nullable |
| `key` | `text` |  |
| `value` | `jsonb` |  Nullable |
| `textValueDeprecated` | `text` |  Nullable |
| `type` | `keyValuePair_type_enum` |  |
| `createdAt` | `timestamptz` |  |
| `updatedAt` | `timestamptz` |  |
| `deletedAt` | `timestamptz` |  Nullable |

## Table `objectMetadata`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `standardId` | `uuid` |  Nullable |
| `dataSourceId` | `uuid` |  |
| `nameSingular` | `varchar` |  |
| `namePlural` | `varchar` |  |
| `labelSingular` | `varchar` |  |
| `labelPlural` | `varchar` |  |
| `description` | `text` |  Nullable |
| `icon` | `varchar` |  Nullable |
| `standardOverrides` | `jsonb` |  Nullable |
| `targetTableName` | `varchar` |  |
| `isCustom` | `bool` |  |
| `isRemote` | `bool` |  |
| `isActive` | `bool` |  |
| `isSystem` | `bool` |  |
| `isUIReadOnly` | `bool` |  |
| `isAuditLogged` | `bool` |  |
| `isSearchable` | `bool` |  |
| `duplicateCriteria` | `jsonb` |  Nullable |
| `shortcut` | `varchar` |  Nullable |
| `labelIdentifierFieldMetadataId` | `uuid` |  Nullable |
| `imageIdentifierFieldMetadataId` | `uuid` |  Nullable |
| `isLabelSyncedWithName` | `bool` |  |
| `workspaceId` | `uuid` |  |
| `createdAt` | `timestamptz` |  |
| `updatedAt` | `timestamptz` |  |
| `applicationId` | `uuid` |  Nullable |
| `universalIdentifier` | `uuid` |  Nullable |

## Table `objectPermission`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `roleId` | `uuid` |  |
| `objectMetadataId` | `uuid` |  |
| `canReadObjectRecords` | `bool` |  Nullable |
| `canUpdateObjectRecords` | `bool` |  Nullable |
| `canSoftDeleteObjectRecords` | `bool` |  Nullable |
| `canDestroyObjectRecords` | `bool` |  Nullable |
| `workspaceId` | `uuid` |  |
| `createdAt` | `timestamptz` |  |
| `updatedAt` | `timestamptz` |  |

## Table `pageLayout`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `name` | `varchar` |  |
| `workspaceId` | `uuid` |  |
| `type` | `pageLayout_type_enum` |  |
| `objectMetadataId` | `uuid` |  Nullable |
| `createdAt` | `timestamptz` |  |
| `updatedAt` | `timestamptz` |  |
| `deletedAt` | `timestamptz` |  Nullable |

## Table `pageLayoutTab`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `title` | `varchar` |  |
| `workspaceId` | `uuid` |  |
| `position` | `float8` |  |
| `pageLayoutId` | `uuid` |  |
| `createdAt` | `timestamptz` |  |
| `updatedAt` | `timestamptz` |  |
| `deletedAt` | `timestamptz` |  Nullable |

## Table `pageLayoutWidget`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `pageLayoutTabId` | `uuid` |  |
| `workspaceId` | `uuid` |  |
| `title` | `varchar` |  |
| `type` | `pageLayoutWidget_type_enum` |  |
| `objectMetadataId` | `uuid` |  Nullable |
| `gridPosition` | `jsonb` |  |
| `configuration` | `jsonb` |  Nullable |
| `createdAt` | `timestamptz` |  |
| `updatedAt` | `timestamptz` |  |
| `deletedAt` | `timestamptz` |  Nullable |

## Table `permissionFlag`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `roleId` | `uuid` |  |
| `flag` | `varchar` |  |
| `workspaceId` | `uuid` |  |
| `createdAt` | `timestamptz` |  |
| `updatedAt` | `timestamptz` |  |

## Table `postgresCredentials`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `user` | `varchar` |  |
| `passwordHash` | `varchar` |  |
| `createdAt` | `timestamptz` |  |
| `updatedAt` | `timestamptz` |  |
| `deletedAt` | `timestamptz` |  Nullable |
| `workspaceId` | `uuid` |  |

## Table `publicDomain`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `createdAt` | `timestamptz` |  |
| `updatedAt` | `timestamptz` |  |
| `domain` | `varchar` |  Unique |
| `isValidated` | `bool` |  |
| `workspaceId` | `uuid` |  |

## Table `remoteServer`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `foreignDataWrapperId` | `uuid` |  |
| `foreignDataWrapperType` | `text` |  Nullable |
| `label` | `text` |  Nullable |
| `foreignDataWrapperOptions` | `jsonb` |  Nullable |
| `userMappingOptions` | `jsonb` |  Nullable |
| `schema` | `text` |  Nullable |
| `workspaceId` | `uuid` |  |
| `createdAt` | `timestamptz` |  |
| `updatedAt` | `timestamptz` |  |

## Table `remoteTable`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `distantTableName` | `varchar` |  |
| `localTableName` | `varchar` |  |
| `workspaceId` | `uuid` |  |
| `remoteServerId` | `uuid` |  |
| `createdAt` | `timestamptz` |  |
| `updatedAt` | `timestamptz` |  |

## Table `role`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `standardId` | `uuid` |  Nullable |
| `label` | `varchar` |  |
| `canUpdateAllSettings` | `bool` |  |
| `canAccessAllTools` | `bool` |  |
| `canReadAllObjectRecords` | `bool` |  |
| `canUpdateAllObjectRecords` | `bool` |  |
| `canSoftDeleteAllObjectRecords` | `bool` |  |
| `canDestroyAllObjectRecords` | `bool` |  |
| `description` | `text` |  Nullable |
| `icon` | `varchar` |  Nullable |
| `workspaceId` | `uuid` |  |
| `createdAt` | `timestamptz` |  |
| `updatedAt` | `timestamptz` |  |
| `isEditable` | `bool` |  |
| `canBeAssignedToUsers` | `bool` |  |
| `canBeAssignedToAgents` | `bool` |  |
| `canBeAssignedToApiKeys` | `bool` |  |
| `universalIdentifier` | `uuid` |  Nullable |
| `applicationId` | `uuid` |  Nullable |

## Table `roleTargets`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `workspaceId` | `uuid` |  |
| `roleId` | `uuid` |  |
| `userWorkspaceId` | `uuid` |  Nullable |
| `agentId` | `uuid` |  Nullable |
| `apiKeyId` | `uuid` |  Nullable |
| `createdAt` | `timestamptz` |  |
| `updatedAt` | `timestamptz` |  |

## Table `routeTrigger`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `universalIdentifier` | `uuid` |  Nullable |
| `id` | `uuid` | Primary |
| `path` | `varchar` |  |
| `isAuthRequired` | `bool` |  |
| `httpMethod` | `routeTrigger_httpmethod_enum` |  |
| `workspaceId` | `uuid` |  |
| `createdAt` | `timestamptz` |  |
| `updatedAt` | `timestamptz` |  |
| `serverlessFunctionId` | `uuid` |  |
| `applicationId` | `uuid` |  Nullable |

## Table `searchFieldMetadata`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `objectMetadataId` | `uuid` |  |
| `fieldMetadataId` | `uuid` |  |
| `createdAt` | `timestamptz` |  |
| `updatedAt` | `timestamptz` |  |
| `workspaceId` | `uuid` |  |

## Table `serverlessFunction`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `name` | `varchar` |  |
| `description` | `varchar` |  Nullable |
| `latestVersion` | `varchar` |  Nullable |
| `publishedVersions` | `jsonb` |  |
| `runtime` | `varchar` |  |
| `timeoutSeconds` | `int4` |  |
| `workspaceId` | `uuid` |  |
| `createdAt` | `timestamptz` |  |
| `updatedAt` | `timestamptz` |  |
| `deletedAt` | `timestamptz` |  Nullable |
| `universalIdentifier` | `uuid` |  Nullable |
| `applicationId` | `uuid` |  Nullable |
| `checksum` | `text` |  Nullable |
| `serverlessFunctionLayerId` | `uuid` |  |

## Table `serverlessFunctionLayer`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `packageJson` | `jsonb` |  |
| `yarnLock` | `text` |  |
| `checksum` | `text` |  |
| `workspaceId` | `uuid` |  |
| `createdAt` | `timestamptz` |  |
| `updatedAt` | `timestamptz` |  |

## Table `twoFactorAuthenticationMethod`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `userWorkspaceId` | `uuid` |  |
| `secret` | `text` |  |
| `status` | `twoFactorAuthenticationMethod_status_enum` |  |
| `strategy` | `twoFactorAuthenticationMethod_strategy_enum` |  |
| `createdAt` | `timestamptz` |  |
| `updatedAt` | `timestamptz` |  |
| `deletedAt` | `timestamptz` |  Nullable |

## Table `user`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `firstName` | `varchar` |  |
| `lastName` | `varchar` |  |
| `email` | `varchar` |  |
| `defaultAvatarUrl` | `varchar` |  Nullable |
| `isEmailVerified` | `bool` |  |
| `disabled` | `bool` |  |
| `passwordHash` | `varchar` |  Nullable |
| `canImpersonate` | `bool` |  |
| `canAccessFullAdminPanel` | `bool` |  |
| `createdAt` | `timestamptz` |  |
| `updatedAt` | `timestamptz` |  |
| `deletedAt` | `timestamptz` |  Nullable |
| `locale` | `varchar` |  |

## Table `userWorkspace`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `userId` | `uuid` |  |
| `workspaceId` | `uuid` |  |
| `defaultAvatarUrl` | `varchar` |  Nullable |
| `locale` | `varchar` |  |
| `createdAt` | `timestamptz` |  |
| `updatedAt` | `timestamptz` |  |
| `deletedAt` | `timestamptz` |  Nullable |

## Table `view`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `universalIdentifier` | `uuid` |  Nullable |
| `id` | `uuid` | Primary |
| `name` | `text` |  |
| `objectMetadataId` | `uuid` |  |
| `type` | `view_type_enum` |  |
| `key` | `view_key_enum` |  Nullable |
| `icon` | `text` |  |
| `position` | `float8` |  |
| `isCompact` | `bool` |  |
| `isCustom` | `bool` |  |
| `openRecordIn` | `view_openrecordin_enum` |  |
| `kanbanAggregateOperation` | `view_kanbanaggregateoperation_enum` |  Nullable |
| `kanbanAggregateOperationFieldMetadataId` | `uuid` |  Nullable |
| `workspaceId` | `uuid` |  |
| `createdAt` | `timestamptz` |  |
| `updatedAt` | `timestamptz` |  |
| `deletedAt` | `timestamptz` |  Nullable |
| `anyFieldFilterValue` | `text` |  Nullable |
| `calendarLayout` | `view_calendarlayout_enum` |  Nullable |
| `calendarFieldMetadataId` | `uuid` |  Nullable |
| `applicationId` | `uuid` |  Nullable |

## Table `viewField`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `universalIdentifier` | `uuid` |  Nullable |
| `id` | `uuid` | Primary |
| `fieldMetadataId` | `uuid` |  |
| `isVisible` | `bool` |  |
| `size` | `int4` |  |
| `position` | `float8` |  |
| `aggregateOperation` | `viewField_aggregateoperation_enum` |  Nullable |
| `viewId` | `uuid` |  |
| `workspaceId` | `uuid` |  |
| `createdAt` | `timestamptz` |  |
| `updatedAt` | `timestamptz` |  |
| `deletedAt` | `timestamptz` |  Nullable |
| `applicationId` | `uuid` |  Nullable |

## Table `viewFilter`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `universalIdentifier` | `uuid` |  Nullable |
| `id` | `uuid` | Primary |
| `fieldMetadataId` | `uuid` |  |
| `operand` | `viewFilter_operand_enum` |  |
| `value` | `jsonb` |  |
| `viewFilterGroupId` | `uuid` |  Nullable |
| `positionInViewFilterGroup` | `float8` |  Nullable |
| `subFieldName` | `text` |  Nullable |
| `viewId` | `uuid` |  |
| `workspaceId` | `uuid` |  |
| `createdAt` | `timestamptz` |  |
| `updatedAt` | `timestamptz` |  |
| `deletedAt` | `timestamptz` |  Nullable |
| `applicationId` | `uuid` |  Nullable |

## Table `viewFilterGroup`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `universalIdentifier` | `uuid` |  Nullable |
| `id` | `uuid` | Primary |
| `parentViewFilterGroupId` | `uuid` |  Nullable |
| `logicalOperator` | `viewFilterGroup_logicaloperator_enum` |  |
| `positionInViewFilterGroup` | `float8` |  Nullable |
| `viewId` | `uuid` |  |
| `workspaceId` | `uuid` |  |
| `createdAt` | `timestamptz` |  |
| `updatedAt` | `timestamptz` |  |
| `deletedAt` | `timestamptz` |  Nullable |
| `applicationId` | `uuid` |  Nullable |

## Table `viewGroup`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `universalIdentifier` | `uuid` |  Nullable |
| `id` | `uuid` | Primary |
| `fieldMetadataId` | `uuid` |  |
| `isVisible` | `bool` |  |
| `fieldValue` | `text` |  |
| `position` | `float8` |  |
| `viewId` | `uuid` |  |
| `workspaceId` | `uuid` |  |
| `createdAt` | `timestamptz` |  |
| `updatedAt` | `timestamptz` |  |
| `deletedAt` | `timestamptz` |  Nullable |
| `applicationId` | `uuid` |  Nullable |

## Table `viewSort`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `universalIdentifier` | `uuid` |  Nullable |
| `id` | `uuid` | Primary |
| `fieldMetadataId` | `uuid` |  |
| `direction` | `viewSort_direction_enum` |  |
| `viewId` | `uuid` |  |
| `workspaceId` | `uuid` |  |
| `createdAt` | `timestamptz` |  |
| `updatedAt` | `timestamptz` |  |
| `deletedAt` | `timestamptz` |  Nullable |
| `applicationId` | `uuid` |  Nullable |

## Table `webhook`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `targetUrl` | `varchar` |  |
| `operations` | `_text` |  |
| `description` | `varchar` |  Nullable |
| `secret` | `varchar` |  |
| `workspaceId` | `uuid` |  |
| `createdAt` | `timestamptz` |  |
| `updatedAt` | `timestamptz` |  |
| `deletedAt` | `timestamptz` |  Nullable |

## Table `workspace`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `displayName` | `varchar` |  Nullable |
| `logo` | `varchar` |  Nullable |
| `inviteHash` | `varchar` |  Nullable |
| `deletedAt` | `timestamptz` |  Nullable |
| `createdAt` | `timestamptz` |  |
| `updatedAt` | `timestamptz` |  |
| `allowImpersonation` | `bool` |  |
| `isPublicInviteLinkEnabled` | `bool` |  |
| `activationStatus` | `workspace_activationStatus_enum` |  |
| `metadataVersion` | `int4` |  |
| `databaseUrl` | `varchar` |  |
| `databaseSchema` | `varchar` |  |
| `subdomain` | `varchar` |  Unique |
| `customDomain` | `varchar` |  Nullable Unique |
| `isGoogleAuthEnabled` | `bool` |  |
| `isTwoFactorAuthenticationEnforced` | `bool` |  |
| `isPasswordAuthEnabled` | `bool` |  |
| `isMicrosoftAuthEnabled` | `bool` |  |
| `isCustomDomainEnabled` | `bool` |  |
| `defaultRoleId` | `uuid` |  Nullable |
| `version` | `varchar` |  Nullable |
| `trashRetentionDays` | `int4` |  |
| `routerModel` | `varchar` |  |

## Table `workspaceMigration`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `migrations` | `jsonb` |  Nullable |
| `name` | `varchar` |  |
| `isCustom` | `bool` |  |
| `appliedAt` | `timestamptz` |  Nullable |
| `workspaceId` | `uuid` |  |
| `createdAt` | `timestamptz` |  |

## Table `workspaceSSOIdentityProvider`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `name` | `varchar` |  |
| `status` | `workspaceSSOIdentityProvider_status_enum` |  |
| `workspaceId` | `uuid` |  |
| `createdAt` | `timestamptz` |  |
| `updatedAt` | `timestamptz` |  |
| `type` | `workspaceSSOIdentityProvider_type_enum` |  |
| `issuer` | `varchar` |  |
| `clientID` | `varchar` |  Nullable |
| `clientSecret` | `varchar` |  Nullable |
| `ssoURL` | `varchar` |  Nullable |
| `certificate` | `varchar` |  Nullable |
| `fingerprint` | `varchar` |  Nullable |

